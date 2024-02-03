+++
title = "Hello Rectangle!"
weight = 2
+++

<style>

#dom-gui {

    display: flex;
    justify-content: center;
    gap: 1rem;

}

button {

    padding: 1rem;
    cursor: pointer;

    background: #A9FDAC;

    border-radius: .5rem;

    outline: none;
    border: none;

    transition-duration: 0.2s;

    width: 100%;

    box-shadow: 0 4px #32A287;

}

button:hover {

    background: #DFFFC7;

}

button:active {

    background: #32A287;

    transform: translateY(4px);

}

</style>

<!-- Load the Paper.js library -->
<script type = "text/javascript" src = "../../scripts/libs/paperjs/paper-full.min.js"></script>

<!-- Load the Sketch -->
<script type = "text/paperscript" canvas = "paper-canvas">

/*
 * Title:   Hello Rectangle!
 * Author:  hamzberg
 * Version: 0.1
 * Date:    08 September 2023
 *
 * Description:
 *   -
 */

var rect_A = new Shape.Rectangle(10, 10, 120, 40);
rect_A.strokeColor = 'black';
rect_A.fillColor = 'black';

var rect_B = new Shape.Rectangle(200, 10, 40, 120);
rect_B.strokeColor = 'red';
rect_B.fillColor = 'red';

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
    link.download = "hello-rectangle_" + currentDate.getDate() +
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

<div id="dom-gui">
    <button id="exportButton"> Save SVG </button>
</div>

<hr>

## Description

A vertical black rectangle and horizontal red rectangle rest on the canvas, again.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```javascript
var rect_A = new Shape.Rectangle(10, 10, 120, 40);
rect_A.strokeColor = 'black';
rect_A.fillColor = 'black';

var rect_B = new Shape.Rectangle(200, 10, 40, 120);
rect_B.strokeColor = 'red';
rect_B.fillColor = 'red';
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I always have to create at least one rectangle in a programming language to give myself something to look forward to.

