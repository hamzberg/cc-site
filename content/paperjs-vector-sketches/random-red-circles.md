+++
title = "Random Red Circles"
weight = 6
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Paper.js library -->
<script type = "text/javascript" src = "../../scripts/libs/paperjs/paper-full.min.js"></script>

<!-- Load the Sketch -->
<script type = "text/paperscript" canvas = "paper-canvas">

/*
 * Title:   Random Red Circles
 * Author:  hamzberg
 * Version: 0.1
 * Date:    17 September 2023
 *
 * Description:
 *   -
 */

// Change Canvas Size -- W -- H
view.viewSize = new Size(400, 400);

console.log("The view is " + view.size);

var circle = new Path.Circle(new Point(view.size.width / 2, view.size.width / 2), 50);

console.log("The center of view is " + (view.size.width / 2) + " and " + (view.size.width / 2));

circle.fillColor = "red";

var cir_Sym = new Symbol(circle);

for (var i = 0; i < 20; i += 1) {

    var position = view.size * Point.random();
    var placed = cir_Sym.place(position);

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
    link.download = "random-red-circles_" + currentDate.getDate() +
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

Random red circles are placed within the canvas.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```javascript
view.viewSize = new Size(400, 400);

console.log("The view is " + view.size);

var circle = new Path.Circle(new Point(view.size.width / 2, view.size.width / 2), 50);

console.log("The center of view is " + (view.size.width / 2) + " and " + (view.size.width / 2));

circle.fillColor = "red";

var cir_Sym = new Symbol(circle);

for (var i = 0; i < 20; i += 1) {

    var position = view.size * Point.random();
    var placed = cir_Sym.place(position);

}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

"Head empty."
