+++
title = "Micro Grid"
weight = 7
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Micro Grid
 * Author:  hamzberg
 * Version: 0.2
 * Date:    6 January 2024
 *
 * Description:
 *   -
 */

let fuse = true;

function setup() {

    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');

    noFill();

}

function draw() {

    if(fuse == true){

        for(let y_pos = 0; y_pos < height; y_pos += 20) {

            for(let x_pos = 0; x_pos < width; x_pos += 20) {

                circle(x_pos, y_pos, randomGaussian(1, 5));

                square(x_pos + 10, y_pos + 10, randomGaussian(1, 5));

            }

        }

        fuse = false;
    }

}

function fuseTrigger() {

    clear();
    fuse = true;

}

function exportSVG() {

    save("micro-grid_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
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

Randomly sized circles and squares dot the canvas in a grid pattern.

## Instructions

Press the "Regenerate" button to regenerate the sketch. Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```JavaScript
    for(let y_pos = 0; y_pos < height; y_pos += 20) {
        for(let x_pos = 0; x_pos < width; x_pos += 20) {
            circle(x_pos, y_pos, randomGaussian(1, 5));
            square(x_pos + 10, y_pos + 10, randomGaussian(1, 5));
        }
    }
```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I've never played with `randomGaussian()` before. Not sure if it really added anything special.
