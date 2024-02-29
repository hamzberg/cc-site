+++
title = "Raindrops"
weight = 10
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Raindrops
 * Author:  hamzberg
 * Version: 0.2
 * Date:    15 January 2024
 *
 * Notes:
 *   -
 */

let fuse = true;

function setup() {

    let c = createCanvas(600, 600, SVG);
    c.parent('processing-canvas');
    noStroke();

}

function draw() {

    if(fuse == true) {

        for(let i = 0; i < 100; i += 1) {

            fill(
                random([
                    color(63, 137, 166), // Dark Blue
                    color(154, 199, 217) // Light Blue
                ]));

            dropMaker(random(0, width - 25), (Math.log(i) * 100), .5);

        }

        fuse = false;

    }

}

function dropMaker(x_Pos, y_Pos, scale) {

    x_Pos /= scale;
    y_Pos /= scale;

    beginShape();
        vertex((25 + x_Pos) * scale, (0 + y_Pos) * scale);
        bezierVertex((25 + x_Pos) * scale, (25 + y_Pos) * scale,
                     (50 + x_Pos) * scale, (50 + y_Pos) * scale,
                     (50 + x_Pos) * scale, (75 + y_Pos) * scale);
        bezierVertex((50 + x_Pos) * scale, (100 + y_Pos) * scale,
                     (15 + x_Pos) * scale, (125 + y_Pos) * scale,
                     (0 + x_Pos) * scale,  (75 + y_Pos) * scale);
        bezierVertex((0 + x_Pos) * scale,  (50 + y_Pos) * scale,
                     (25 + x_Pos) * scale, (50 + y_Pos) * scale,
                     (25 + x_Pos) * scale, (0 + y_Pos) * scale);
        vertex((25 + x_Pos) * scale, (0 + x_Pos) * scale);
    endShape(CLOSE);

}

function fuseTrigger() {

    clear();
    fuse = true;

}

function exportSVG() {

    save("raindrops_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
    print("SVG Downloaded");

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<div id="dom-gui">
    <button onclick="fuseTrigger()"> Regenerate </button>
    <button onclick="exportSVG()"> Save SVG </button>
</div>

<hr>

## Description

Raindrops are placed randomly based on the log of the first for loop times 100.

## Instructions

Press the "Regenerate" button to regenerate the sketch. Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```JavaScript
let fuse = true;

function setup() {
    noStroke();
}

function draw() {
    if(fuse == true) {
        for(let i = 0; i < 100; i += 1) {
            fill(random([color(63, 137, 166), color(154, 199, 217)]));
            dropMaker(random(0, width - 25), (Math.log(i) * 100), .5);
        }
        fuse = false;
    }
}

function dropMaker(x_Pos, y_Pos, scale) {
    x_Pos /= scale;
    y_Pos /= scale;
    beginShape();
        vertex((25 + x_Pos) * scale, (0 + y_Pos) * scale);
        bezierVertex((25 + x_Pos) * scale, (25 + y_Pos) * scale,
                     (50 + x_Pos) * scale, (50 + y_Pos) * scale,
                     (50 + x_Pos) * scale, (75 + y_Pos) * scale);
        bezierVertex((50 + x_Pos) * scale, (100 + y_Pos) * scale,
                     (15 + x_Pos) * scale, (125 + y_Pos) * scale,
                     (0 + x_Pos) * scale,  (75 + y_Pos) * scale);
        bezierVertex((0 + x_Pos) * scale,  (50 + y_Pos) * scale,
                     (25 + x_Pos) * scale, (50 + y_Pos) * scale,
                     (25 + x_Pos) * scale, (0 + y_Pos) * scale);
        vertex((25 + x_Pos) * scale, (0 + x_Pos) * scale);
    endShape(CLOSE);
}
```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I wanted to play with bezier curves. There's a weird vertex that isn't visible on every raindrop but causes a line to appear on the axidraw. Still looks cool.
