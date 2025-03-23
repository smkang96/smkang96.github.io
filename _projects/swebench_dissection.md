---
layout: page
title: SWE-bench Dissection
description: An analogue to Defects4J Dissection
img: assets/img/12.jpg
importance: 1
category: work
---

Type in a SWE-bench Verified instance ID below to get its information!

<input type="text" id="bug_query" style="text-align:center;width:250px;height:28px;" placeholder="Try: astropy__astropy-12907">

## Info for <code id="bug_name"></code>

The issue for this bug was created at <code id="issue_time"></code>; see the repository state at that time <a href="." id="link_to_code">here</a>. This bug is considered to be <b><span id="difficulty"></span></b>.

### Bug Report

<pre id="bug_report" style="white-space: pre-wrap;"></pre>

### Patch

<pre id="code_patch"></pre>

### Reproducing Test

<pre id="test_patch"></pre>


<script>
    let currentIndex = 0;
    let currentName = "astropy__astropy-12907";
    let data = [];

    // Function to fetch JSON data from file
    async function fetchData(fname) {
        try {
            const response = await fetch(fname);
            const jsonData = await response.json();
            data = jsonData;
        } catch (error) {
            console.error('Error fetching data:', error);
        }
    }

    // Function to display code and documentation
    function displayData(index) {
        const bugNameSpan = document.getElementById('bug_name');
        const timeSpan = document.getElementById('issue_time');
        const linkToCodeA = document.getElementById('link_to_code');
        const difficultySpan = document.getElementById('difficulty');
        const bugReportPre = document.getElementById('bug_report');
        const patchPre = document.getElementById('code_patch');
        const testPre = document.getElementById('test_patch');

        // // Clear previous content
        // codeContainer.innerHTML = '';
        // humanDoc.innerHTML = '';
        // autoDoc.innerHTML = '';

        // Display simple info
        bugNameSpan.textContent = data[index].instance_id;
        timeSpan.textContent = data[index].created_at;
        linkToCodeA.href = `https://github.com/${data[index].repo}/tree/${data[index].base_commit}`;
        difficulty_assessment = data[index].difficulty;
        var difficulty_category = 'Very easy';
        if (difficulty_assessment == ">4 hours") {
            difficulty_category = 'Hard';
        } else if (difficulty_assessment == "1-4 hours") {
            difficulty_category = 'Moderate';
        } else if (difficulty_assessment == "15 min - 1 hour") {
            difficulty_category = 'Easy';
        }
        difficultySpan.textContent = difficulty_category + ` (${difficulty_assessment} of human effort)`;

        // Display code
        bugReportPre.textContent = data[index].problem_statement;
        patchPre.textContent = data[index].patch;
        testPre.textContent = data[index].test_patch;
    }

    // Call fetchData function when the page loads
    window.onload = function(){;};
    fetchData("/assets/json/swebench_verified.json")

    function displayDataFromInputName() {
        var input_id = $('#bug_query').val();
        for (let i=0; i<data.length; i++) {
            if (data[i].instance_id == input_id) {
                displayData(i);
                return;
            }
        }
        alert(`Your query ${input_id} was not found.`)
    }

    $(document).keydown(function(e) {
        if (e.target.nodeName == "INPUT") {
            if (e.keyCode == 13) {
                displayDataFromInputName();
            }
        } else {
            if (e.keyCode == 37) {
                displayData(currentIndex-1)
            } else if (e.keyCode == 39) {
                displayData(currentIndex+1)
            }
        }
    });

</script>