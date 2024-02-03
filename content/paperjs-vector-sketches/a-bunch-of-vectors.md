+++
title = "A Bunch of Vectors"
weight = 3
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
 * Title:   A Bunch of Vectors
 * Author:  hamzberg
 * Version: 1.1
 * Date:    08 September 2023
 *
 * Description:
 *   -
 */

var point_A = new Point();
var point_B = new Point(50, 50);

var vector_AB = point_B - point_A;

var path_AB = new Path([point_B, point_A]);
path_AB.strokeColor = 'black';

console.log("The value of vector_AB is " + vector_AB);
console.log("The angle of vector_AB is " + vector_AB.angle);
console.log("The length of vector_AB is " + vector_AB.length);

var point_C = new Point(23, 36);
var point_D = new Point(45, 57);

var point_E = new Point(25, 70);
var point_F = new Point(145, 125);

var vector_CD = point_C - point_D;
var vector_EF = point_E - point_F;

var path_CD = new Path([point_C, point_D]);
path_CD.strokeColor = 'red';
var path_EF = new Path([point_E, point_F]);
path_EF.strokeColor = 'blue';

var vector_CDEF = vector_CD - vector_EF;
console.log("The location of vector_CDEF is " + vector_CDEF);

var path_CDEF = new Path([vector_CD, vector_EF]);
path_CDEF.strokeColor = 'green';

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
    link.download = "a-bunch-of-vectors_" + currentDate.getDate() +
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

Exploration into the math involved with vectors.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```javascript
var point_A = new Point();
var point_B = new Point(50, 50);

var vector_AB = point_B - point_A;

var path_AB = new Path([point_B, point_A]);
path_AB.strokeColor = 'black';

console.log("The value of vector_AB is " + vector_AB);
console.log("The angle of vector_AB is " + vector_AB.angle);
console.log("The length of vector_AB is " + vector_AB.length);

var point_C = new Point(23, 36);
var point_D = new Point(45, 57);

var point_E = new Point(25, 70);
var point_F = new Point(145, 125);

var vector_CD = point_C - point_D;
var vector_EF = point_E - point_F;

var path_CD = new Path([point_C, point_D]);
path_CD.strokeColor = 'red';
var path_EF = new Path([point_E, point_F]);
path_EF.strokeColor = 'blue';

var vector_CDEF = vector_CD - vector_EF;
console.log("The location of vector_CDEF is " + vector_CDEF);

var path_CDEF = new Path([vector_CD, vector_EF]);
path_CDEF.strokeColor = 'green';
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

It's simple math.
