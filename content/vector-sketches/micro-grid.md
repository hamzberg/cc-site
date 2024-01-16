+++
title = "Micro Grid"
weight = 5
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Micro Grid
 * Author:  hamzberg
 * Version: 0.1
 * Date:    6 January 2024
 *
 * Description:
 *   -
 */

function setup() {

    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');

    for(let y_pos = 0; y_pos < height; y_pos += 20) {

        for(let x_pos = 0; x_pos < width; x_pos += 20) {

            circle(x_pos, y_pos, randomGaussian(1, 5));

            square(x_pos + 10, y_pos + 10, randomGaussian(1, 5));

        }

    }

}


function draw() {

    exportSVG();

}

function exportSVG() {

    if (keyCode === LEFT_ARROW) {
        save("micro-grid_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
        print("SVG Downloaded");
        noLoop();
    }

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<hr>

## Description

Randomly sized circles and squares dot the canvas in a grid pattern.

## Instructions

Refresh the page to regenerate the sketch. Press the Left Arrow key to save an SVG.

## Code Sample

```JavaScript
    for(let y_pos = 0; y_pos < height; y_pos += 20) {
        for(let x_pos = 0; x_pos < width; x_pos += 20) {
            circle(x_pos, y_pos, randomGaussian(1, 5));
            square(x_pos + 10, y_pos + 10, randomGaussian(1, 5));
        }
    }
```
## Thoughts

I've never played with `randomGaussian()` before. Not sure if it really added anything special.
