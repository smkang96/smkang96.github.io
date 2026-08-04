---
layout: page
title: QR generator
description: client-side and immediate
img: assets/img/website_qr.png
importance: 3
category: work
---

Input text below to make a QR code.

<input
    type="text"
    id="qr_input"
    style="text-align:center;width:400px;height:28px;"
    placeholder="https://example.com">

<br><br>

<div id="qr_container"></div>

<style>
#qr_container {
    display: flex;
    justify-content: center;
    margin-top: 20px;
}

#qr_canvas {
    display: block;
}
</style>

<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>

<script>
function generateQR() {
    const text = document.getElementById("qr_input").value.trim();
    const container = document.getElementById("qr_container");

    container.innerHTML = "";

    if (!text) return;

    // Temporary QR generation area
    const temp = document.createElement("div");

    new QRCode(temp, {
        text: text,
        width: 256,
        height: 256,
        correctLevel: QRCode.CorrectLevel.H
    });

    setTimeout(() => {
        const qrImage = temp.querySelector("img") || temp.querySelector("canvas");

        const finalCanvas = document.createElement("canvas");
        const margin = 20; // actual white border in the image
        const size = 256 + margin * 2;

        finalCanvas.width = size;
        finalCanvas.height = size;

        const ctx = finalCanvas.getContext("2d");

        // Real white background
        ctx.fillStyle = "white";
        ctx.fillRect(0, 0, size, size);

        // Draw QR with embedded margin
        ctx.drawImage(qrImage, margin, margin, 256, 256);

        finalCanvas.id = "qr_canvas";

        container.appendChild(finalCanvas);
    }, 200);
}

document.getElementById("qr_input").addEventListener("keydown", function(e) {
    if (e.key === "Enter") {
        generateQR();
    }
});
</script>

<details>
<summary>Motivation</summary>
If you search for "free qr code generator" on Google, most of the top websites will ask for you to make an account and log in. This is frustrating, especially when they ask to make an account _after_ you put in the information for the QR. I don't really understand why it's hard to find an easy-to-use, client-side, vanilla QR code generating website without fuss, so I made one. (Er, ChatGPT wrote the code, and I hosted it here for my convenience.) <br><br>

You might ask, doesn't Chrome generate QR codes? Yes, but it comes with a specific pointillism-esque style, with the dinosaur in the center, which makes it obvious that you got the QR code from Chrome. I want to be lazy, but not blatantly so.
</details>