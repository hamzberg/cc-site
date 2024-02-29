+++
title = "Shapes and Shaping"
weight = 4
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Paper.js library -->
<script type = "text/javascript" src = "../../scripts/libs/paperjs/paper-full.min.js"></script>

<!-- Load the Sketch -->
<script type = "text/paperscript" canvas = "paper-canvas">

/*
 * Title:   Shapes and Shaping
 * Author:  hamzberg
 * Version: 0.1
 * Date:    12 September 2023
 *
 * Description:
 *   -
 */

// Declares path and then inserts a point at a specific point
var path_A = new Path();

path_A.strokeColor = 'black';
path_A.add(new Point(0, 0), new Point(100, 50));

path_A.insert(1, new Point(30, 40));


// Path Smoothing and closing

var path_B = new Path();

path_B.strokeColor = 'black';
path_B.add(new Point(130, 75));
path_B.add(new Point(130, 25));
path_B.add(new Point(180, 25));
path_B.add(new Point(180, 75));
path_B.closed = true;

path_B.fullySelected = true;

var copy_Path_B = path_B.clone();
copy_Path_B.selected = true;
copy_Path_B.position.x += 100;

copy_Path_B.smooth();

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
    link.download = "shapes-and-shaping_" + currentDate.getDate() +
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

Showcase of PaperJS features, such as the ```.selected``` option and using ```.add``` to insert another point on a path.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Source

```javascript
var path_A = new Path();

path_A.strokeColor = 'black';
path_A.add(new Point(0, 0), new Point(100, 50));

path_A.insert(1, new Point(30, 40));

var path_B = new Path();

path_B.strokeColor = 'black';
path_B.add(new Point(130, 75));
path_B.add(new Point(130, 25));
path_B.add(new Point(180, 25));
path_B.add(new Point(180, 75));
path_B.closed = true;

path_B.fullySelected = true;

var copy_Path_B = path_B.clone();
copy_Path_B.selected = true;
copy_Path_B.position.x += 100;

copy_Path_B.smooth();
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

The ```.selected``` is so odd to me. It really reminds me of vector programs, which isn't surprising knowing this library's origins, but still.

