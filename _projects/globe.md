---
layout: page
title: A Globe
description: of where I've been
img: assets/img/globe_still.png
importance: 1
category: fun
---

<div id="globe-wrap">
  <div id="globe-controls">
    <label for="globe-speed">rotation speed</label>
    <input id="globe-speed" type="range" min="0" max="0.6" step="0.01" value="0.02"
           aria-label="rotation speed">
  </div>
  <pre id="globe" aria-label="rotating ASCII globe of visited places"></pre>
</div>

<style>
#globe-wrap { text-align: center; }
#globe {
  font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
  line-height: 1;
  letter-spacing: 0;
  white-space: pre;
  margin: 0 auto;
  padding: 0;
  border: 0;
  background: none;
  overflow: hidden;
  user-select: none;
  font-variant-ligatures: none;
}
/* Explicit cartographic palette rather than the site theme colors, nudged
   per theme so both greens keep contrast against the page background. */
#globe-wrap {
  --sea: #1b4674;
  --unvisited: #1b6b3c;
  --visited: #2fbe63;
}
html[data-theme='dark'] #globe-wrap {
  --sea: #24507f;
  --unvisited: #1f7a44;
  --visited: #6ae88f;
}
#globe .o { color: var(--sea); }
#globe .l { color: var(--unvisited); }
#globe .v { color: var(--visited); font-weight: 700; }
#globe-controls {
  margin-bottom: 0.8rem;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.6rem;
}
#globe-controls label { font-size: 0.8rem; color: var(--global-text-color-light); margin: 0; }
#globe-speed { width: 190px; accent-color: var(--global-theme-color); }
</style>

<script defer src="https://cdn.jsdelivr.net/npm/d3@7/dist/d3.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/topojson-client@3/dist/topojson-client.min.js"></script>

<script>
window.addEventListener("load", function () {
  // Natural Earth 110m keys countries by ISO 3166-1 *numeric*, so the alpha-3
  // list is mapped over. Singapore and Vatican City do not survive the 110m
  // generalization and are painted onto the raster by hand.
  const VISITED = new Set([
    "116", "156", "268", "360", "392", "458", "608", "410", "764", "860",
    "704", "124", "840", "076", "040", "203", "250", "276", "300", "348",
    "380", "620", "724", "756", "036", "554", "096", "158",
  ]);
  const MICRO = [
    { lon: 103.82, lat: 1.35 },   // Singapore
    { lon: 12.45, lat: 41.90 },   // Vatican City
  ];
  // Sea is a flat minimum-weight character. Land picks from this ramp by how
  // much of the cell the land actually covers, so coastlines antialias into
  // the sea instead of stair-stepping.
  const SEA = ".";
  const LAND = ".:-=+*#%@";
  const OCEAN_C = 0, LAND_C = 1, VISITED_C = 2;
  const CLS = ["o", "l", "v"];

  // Subsamples per axis inside each character cell. SS*SS coverage buckets,
  // so this is the knob for how finely coastlines gradate.
  const SS = 4;

  const D2R = Math.PI / 180, R2D = 180 / Math.PI;
  const PITCH = 20 * D2R; // fixed tilt toward the viewer
  const pre = document.getElementById("globe");
  const slider = document.getElementById("globe-speed");

  // ---- classification raster ------------------------------------------------
  // An equirectangular bitmap is rasterized once, so the animation loop never
  // touches geometry.
  const RW = 1440, RH = 720;
  let raster = null; // Uint8Array of OCEAN_C / LAND_C / VISITED_C

  function buildRaster(world) {
    const features = topojson.feature(world, world.objects.countries).features;

    const cv = document.createElement("canvas");
    cv.width = RW;
    cv.height = RH;
    const c = cv.getContext("2d", { willReadFrequently: true });

    const proj = d3.geoEquirectangular().scale(RW / (2 * Math.PI)).translate([RW / 2, RH / 2]);
    const gp = d3.geoPath(proj, c);

    // Land carries blue, visited carries red *and* blue. Both are recovered by
    // thresholding, which makes the readback immune to path antialiasing.
    c.fillStyle = "#0000ff";
    c.beginPath();
    gp({ type: "FeatureCollection", features: features });
    c.fill();

    c.fillStyle = "#ff00ff";
    c.beginPath();
    gp({ type: "FeatureCollection", features: features.filter((f) => VISITED.has(f.id)) });
    c.fill();

    // A 0.25 degree pixel cannot hold Singapore, so the micro-states are drawn
    // oversized -- about one character wide at the default grid.
    MICRO.forEach((m) => {
      const p = proj([m.lon, m.lat]);
      c.beginPath();
      c.arc(p[0], p[1], 7, 0, 2 * Math.PI);
      c.fill();
    });

    const px = c.getImageData(0, 0, RW, RH).data;
    raster = new Uint8Array(RW * RH);
    for (let i = 0, j = 0; i < raster.length; i++, j += 4) {
      raster[i] = px[j] > 127 ? VISITED_C : (px[j + 2] > 127 ? LAND_C : OCEAN_C);
    }
  }

  function sample(lon, lat) {
    let x = ((lon + 180) / 360 * RW) | 0;
    let y = ((90 - lat) / 180 * RH) | 0;
    if (x < 0) x = 0; else if (x >= RW) x = RW - 1;
    if (y < 0) y = 0; else if (y >= RH) y = RH - 1;
    return raster[y * RW + x];
  }

  // ---- grid geometry --------------------------------------------------------
  let cols = 0, rows = 0, cx = 0, cy = 0, Rc = 0, Rr = 0, ratio = 0.6;

  function measureRatio() {
    const s = document.createElement("span");
    s.style.cssText = "position:absolute;visibility:hidden;white-space:pre;font-size:100px;line-height:1;letter-spacing:0";
    s.style.fontFamily = getComputedStyle(pre).fontFamily;
    s.textContent = "M".repeat(50);
    document.body.appendChild(s);
    const r = s.getBoundingClientRect().width / 50 / 100;
    s.remove();
    return r || 0.6;
  }

  function layout() {
    const width = pre.parentElement.clientWidth;
    if (!width) return;
    ratio = measureRatio();
    cols = width < 520 ? 74 : 116;
    // Square on screen: rows * cellH == cols * cellW, and cellH == fontSize.
    rows = Math.round(cols * ratio);
    const fontSize = width / (cols * ratio);
    pre.style.fontSize = fontSize + "px";
    pre.style.width = width + "px";
    cx = (cols - 1) / 2;
    cy = (rows - 1) / 2;
    Rc = cols / 2 - 0.5;
    Rr = Rc * ratio;
    buildGrid();
    draw();
  }

  // ---- subsample cache ------------------------------------------------------
  // Spinning only adds a constant to longitude, and the tilt is fixed, so the
  // latitude and *unrotated* longitude of every subsample are computed once.
  // Each frame is then an add and an array lookup, with no trigonometry at all
  // -- which is what makes SS*SS supersampling affordable per frame.
  let gLat = null, gLon0 = null, gIn = null;

  function buildGrid() {
    if (!cols) return;
    const n = cols * rows * SS * SS;
    if (!gLat || gLat.length !== n) {
      gLat = new Float32Array(n);
      gLon0 = new Float32Array(n);
      gIn = new Uint8Array(n);
    }
    const cp = Math.cos(PITCH), sp = Math.sin(PITCH);
    let i = 0;
    for (let r = 0; r < rows; r++) {
      for (let c = 0; c < cols; c++) {
        for (let sy = 0; sy < SS; sy++) {
          const yv = -((r + (sy + 0.5) / SS - 0.5) - cy) / Rr;
          for (let sx = 0; sx < SS; sx++, i++) {
            const xv = ((c + (sx + 0.5) / SS - 0.5) - cx) / Rc;
            const q = xv * xv + yv * yv;
            if (q > 1) { gIn[i] = 0; continue; }
            const zv = Math.sqrt(1 - q);
            gIn[i] = 1;
            gLat[i] = Math.asin(yv * cp + zv * sp) * R2D;
            gLon0[i] = Math.atan2(xv, zv * cp - yv * sp) * R2D;
          }
        }
      }
    }
  }

  let yaw = 120 * D2R; // longitude at the center of the disc, positive east

  function draw() {
    if (!raster || !gIn) return;
    const yawDeg = yaw * R2D;
    const SS2 = SS * SS;
    const top = LAND.length - 1;
    let html = "";
    let i = 0;
    for (let r = 0; r < rows; r++) {
      let runCls = -1, run = "";
      for (let c = 0; c < cols; c++) {
        let nIn = 0, nLand = 0, nVis = 0;
        for (let s = 0; s < SS2; s++, i++) {
          if (!gIn[i]) continue;
          nIn++;
          let lon = gLon0[i] + yawDeg;
          lon = ((lon + 180) % 360 + 360) % 360 - 180;
          const k = sample(lon, gLat[i]);
          if (k === VISITED_C) nVis++;
          else if (k === LAND_C) nLand++;
        }

        let cls, ch;
        const land = nLand + nVis;
        if (nIn === 0) {
          cls = -1;
          ch = " ";
        } else if (land === 0) {
          cls = OCEAN_C;
          ch = SEA;
        } else {
          // Whichever kind of land holds the cell decides the color; the
          // fraction of the cell that is land at all decides the weight.
          // Coverage is taken over the subsamples inside the disc, so cells
          // straddling the limb are not dimmed for being half off-globe.
          cls = nVis > nLand ? VISITED_C : LAND_C;
          let idx = Math.ceil((land / nIn) * LAND.length) - 1;
          if (idx < 0) idx = 0; else if (idx > top) idx = top;
          ch = LAND[idx];
        }

        if (cls !== runCls) {
          if (run) html += runCls === -1 ? run : '<span class="' + CLS[runCls] + '">' + run + "</span>";
          runCls = cls;
          run = "";
        }
        run += ch;
      }
      if (run) html += runCls === -1 ? run : '<span class="' + CLS[runCls] + '">' + run + "</span>";
      html += "\n";
    }
    pre.innerHTML = html;
  }

  // ---- animation ------------------------------------------------------------
  let speed = +slider.value; // radians per second
  let lastT = 0;
  let acc = 0;
  const FRAME = 1 / 30;

  slider.addEventListener("input", () => { speed = +slider.value; });

  function tick(t) {
    requestAnimationFrame(tick);
    const dt = lastT ? (t - lastT) / 1000 : 0;
    lastT = t;
    if (!raster || speed === 0) return; // nothing moves, nothing to redraw
    acc += dt;
    if (acc < FRAME) return;
    yaw += speed * acc;
    acc = 0;
    draw();
  }
  requestAnimationFrame(tick);

  // ---- boot -----------------------------------------------------------------
  window.addEventListener("resize", layout);
  if (document.fonts && document.fonts.ready) document.fonts.ready.then(layout);

  d3.json("{{ '/assets/json/countries-110m.json' | relative_url }}").then(function (world) {
    buildRaster(world);
    layout();
  });
});
</script>
