+++
title = "Layered Circles"
weight = 5
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Paper.js library -->
<script type = "text/javascript" src = "../../scripts/libs/paperjs/paper-full.min.js"></script>

<!-- Load the Sketch -->
<script type = "text/paperscript" canvas = "paper-canvas">

/*
 * Title:   Layered Sketches
 * Author:  hamzberg
 * Version: 0.1
 * Date:    08 September 2023
 *
 * Description:
 *   -
 */

var circle_A = new Path.Circle(new Point(80, 50), 35);

var circle_B = circle_A.clone();

circle_A.fillColor = 'red';

circle_B.fillColor = 'blue';

for (var i = 0; i < 10; i += 1){

    circle_A.position.x += i;

}

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
    link.download = "layered-circles_" + currentDate.getDate() +
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

A blue circle is layered on top of a red circle.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Source

```javascript
var circle_A = new Path.Circle(new Point(80, 50), 35);

var circle_B = circle_A.clone();

circle_A.fillColor = 'red';

circle_B.fillColor = 'blue';

for (var i = 0; i < 10; i += 1){
    circle_A.position.x += i;
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

More so playing with `.clone`. Nothing remarkable here.
