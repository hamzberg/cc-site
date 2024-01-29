+++
title = "PaperJS Vector Sketch"
weight = 1
+++

<!-- Load the Paper.js library -->
<script type = "text/javascript" src = "../../scripts/libs/paperjs/paper-full.min.js"></script>

<!-- Load the Sketch -->
<script type = "text/paperscript" canvas = "paper-canvas">

/*
 * Title:   PaperJS Sketch No. #
 * Author:  hamzberg
 * Version: 0.0
 * Date:    1 January 2024
 *
 * Description:
 *   -
 */

// Function to export SVG
function exportSVG() {

    // Create a new SVG export item:
    var svg = project.exportSVG({ asString: true });

    // Create a Blob from the SVG string:
    var blob = new Blob([svg], { type: 'image/svg+xml' });

    var currentDate = new Date();

    // Create a download link and trigger the click event:
    var link = document.createElement('a');
    link.href = window.URL.createObjectURL(blob);
    link.download = "temp_" + currentDate.getDate() +
                    "-" + (currentDate.getMonth() + 1) +
                    "-" + currentDate.getFullYear() +
                    "_" + currentDate.getMilliseconds() +
                    ".svg";
    link.click();

}

// Event listener for the export button
document.getElementById('exportButton').addEventListener('click', exportSVG);

</script>

<!-- Insert the Sketch -->
<canvas id="paper-canvas" resize style="width:100%;"></canvas>

<button id="exportButton"> Save SVG </button>

<hr>

## Description

This is a template to use for PaperJS.

## Instructions

Copy the contents of this Markdown file to a new sketch. Remember to change the SVG download file name.

## Code Source

The code for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

"Head empty."
