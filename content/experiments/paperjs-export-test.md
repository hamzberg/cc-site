+++
title = "PaperJS Export Test"
weight = 3
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Paper.js library -->
<script type = "text/javascript" src = "../../scripts/libs/paperjs/paper-full.min.js"></script>

<!-- Load the Sketch -->
<script type = "text/paperscript" canvas = "paper-canvas">

/*
 * Title:   PaperJS Export Test
 * Author:  hamzberg
 * Version: 0.1
 * Date:    27 January 2024
 *
 * Description:
 *   -
 */

var circle = new Path.Circle({
    fillColor: 'blue',
    radius: 10,
    position: [50, 50]
});

var circle_Sym = new Symbol(circle);

for(var x_Position = 10; x_Position < view.size.width - 10; x_Position += 20) {

    for(var y_Position = 10; y_Position < view.size.height - 10; y_Position += 20) {

        var circle_Cont = circle_Sym.place(new Point(x_Position, y_Position));

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
    link.download = "paperjs-export-test_" + currentDate.getDate() +
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

Exports an SVG from a PaperJS canvas.

## Instructions

Press the "Save SVG" button to save the canvas' contents to SVG.

## Code Sample

```javascript
var circle = new Path.Circle({
    fillColor: 'blue',
    radius: 10,
    position: [50, 50]
});

var circle_Sym = new Symbol(circle);

for(var x_Position = 10; x_Position < view.size.width - 10; x_Position += 20) {
    for(var y_Position = 10; y_Position < view.size.height - 10; y_Position += 20) {
        var circle_Cont = circle_Sym.place(new Point(x_Position, y_Position));
    }
}

function exportSVG() {

    var svg = project.exportSVG({ asString: true });

    var blob = new Blob([svg], { type: 'image/svg+xml' });

    var currentDate = new Date();

    var link = document.createElement('a');
    link.href = window.URL.createObjectURL(blob);
    link.download = "paperjs-export-test_" + currentDate.getDate() +
                    "-" + (currentDate.getMonth() + 1) +
                    "-" + currentDate.getFullYear() +
                    "_" + currentDate.getMilliseconds() +
                    ".svg";
    link.click();
}

document.getElementById('exportButton').addEventListener('click', exportSVG);
```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

For a very long time, I struggled to understand how to export an SVG from a PaperJS canvas. I saw a couple solutions online,
notably from [Mike Chambers](https://mikechambers.com/blog/2014/07/01/saving-svg-content-from-paper.js/) and
[Ivan Sifrim](https://medium.com/@ivansifrim/draw-with-javascript-and-export-to-svg-with-paper-js-34a06e5621c0), but they didn't work.

I gave up and asked ChatGPT 3.5 for a solution. What it returned was relatively similar to the ones presented in the links above, but used a
Blob instead of a URL. I believe that somewhere between now and when these guys' articles were published, web browsers changed how
they display local files. Hense why their solutions don't work.

I just wish I had known enough about JavaScript to have figured it out myself. I had no idea what a Blob was. I did see it being used in the PaperJS
[online sketch editor](https://github.com/paperjs/sketch.paperjs.org/blob/master/assets/js/main.js):

```javascript
$('.button.canvas-export-svg', element).click(function() {
    var svg = scope.project.exportSVG({ asString: true });
    this.href = getBlobURL(svg, 'image/svg+xml');
    this.download = 'Export_' + getTimeStamp() + '.svg';
});
```
But, I didn't understand what it was doing at all. I suppose I should've gotten the hint from the `getBlobURL()`.

I changed what ChatGPT gave me only slightly: changing the file name to have the current time after the name. Otherwise, it's the same.
