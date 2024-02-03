+++
title = "Bunch of Smileys"
weight = 7
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
 * Title:   Bunch of Smileys
 * Author:  hamzberg
 * Version: 0.1
 * Date:    29 September 2023
 *
 * Description:
 *   -
 */

// Change Canvas Size -- W -- H
view.viewSize = new Size(700, 300);

// Making the Smiley
var base_face = new Path.Circle({
    center: [100, 100],
    radius: 100,
    fillColor: 'yellow'
});

var left_eye = new Path.Circle({
    center: [50, 75],
    radius: 15,
    fillColor: 'black'
});


var right_eye = new Path.Circle({
    center: [150, 75],
    radius: 15,
    fillColor: 'black'
});

var arc_smile = new Path.Arc({
    from:    [65, 110],
    to:      [165, 110],
    through: [100, 140],
    strokeColor: 'black',
    strokeWidth: 5

});

// Create Smiley Group
var smiley = new Group([
    base_face,
    left_eye,
    right_eye,
    arc_smile
]);

smiley.scale(.25);

var smiley_symdef = new SymbolDefinition(smiley);

for (var i = 0; i < 50; i++) {

    var inst = smiley_symdef.place();
    var rand_ang = new Point(30, 270) * Point.random();

    inst.position = Point.random() * view.size;
    inst.rotate(rand_ang.x);

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
    link.download = "bunch-of-smileys_" + currentDate.getDate() +
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

A bunch of yellow smileys with black facial features are randomly placed within the canvas.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```javascript
view.viewSize = new Size(700, 300);

var base_face = new Path.Circle({
    center: [100, 100],
    radius: 100,
    fillColor: 'yellow'
});

var left_eye = new Path.Circle({
    center: [50, 75],
    radius: 15,
    fillColor: 'black'
});


var right_eye = new Path.Circle({
    center: [150, 75],
    radius: 15,
    fillColor: 'black'
});

var arc_smile = new Path.Arc({
    from:    [65, 110],
    to:      [165, 110],
    through: [100, 140],
    strokeColor: 'black',
    strokeWidth: 5

});

var smiley = new Group([
    base_face,
    left_eye,
    right_eye,
    arc_smile
]);

smiley.scale(.25);

var smiley_symdef = new SymbolDefinition(smiley);

for (var i = 0; i < 50; i++) {
    var inst = smiley_symdef.place();
    var rand_ang = new Point(30, 270) * Point.random();

    inst.position = Point.random() * view.size;
    inst.rotate(rand_ang.x);
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I wanted to finally break out and do something with the knowledge I've gained so far. Smileys are my favorite thing to depict.
