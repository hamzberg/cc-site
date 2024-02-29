+++
title = "Octagon Hilltops"
weight = 8
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Paper.js library -->
<script type = "text/javascript" src = "../../scripts/libs/paperjs/paper-full.min.js"></script>

<!-- Load the Sketch -->
<script type = "text/paperscript" canvas = "paper-canvas">

/*
 * Title:   Octagon Hilltops
 * Author:  hamzberg
 * Version: 0.1
 * Date:    1 January 2024
 *
 * Description:
 *   -
 */

for (var y_pos = 1; y_pos < 1000; y_pos += 150) {

   for (var x_pos = 1; x_pos < 1000; x_pos += 150) {

      for (var i = 1; i < 10; i+= 1) {

         new Path.RegularPolygon({

            center: [x_pos + (i * 2), y_pos + (i * 2)],
            sides: 8,
            radius: 30 * (i / 4),
            strokeColor: 'black',
            strokeWidth: 2

         });

      }

   }

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
    link.download = "octagon-hilltops_" + currentDate.getDate() +
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

A grid of octagons with a shrinking set octagons within each one.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```javascript
for (var y_pos = 1; y_pos < 1000; y_pos += 150) {
   for (var x_pos = 1; x_pos < 1000; x_pos += 150) {
      for (var i = 1; i < 10; i+= 1) {
         new Path.RegularPolygon({
            center: [x_pos + (i * 2), y_pos + (i * 2)],
            sides: 8,
            radius: 30 * (i / 4),
            strokeColor: 'black',
            strokeWidth: 2
         });
      }
   }
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

This was fun. Felt more in line with the stuff I create in p5JS.
