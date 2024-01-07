+++
title = "Descending Arcs"
weight = 4
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Descending Arcs
 * Author:  hamzberg
 * Version: 0.1
 * Date:    6 January 2024
 *
 * Description:
 *   -
 */

function setup() {
    let c = createCanvas(600, 800, SVG);
    c.parent('processing-canvas');

    noFill();

    let polar = 1;

    let shrink = 0;

    for(let y_pos = 0; y_pos < height; y_pos += 50) {

        for(let x_pos = 0; x_pos < width; x_pos += 25) {

            if (polar === 1) {
                arc(x_pos, y_pos, 100 - shrink, 50, HALF_PI, PI + HALF_PI);
            } else {
                arc(x_pos, y_pos, 100 - shrink, 50, PI + HALF_PI, TAU + HALF_PI);
            }

        }

        polar *= -1;

        shrink += 5;
    }

}


function draw() {

    exportSVG();

}

function exportSVG() {

    if (keyCode === LEFT_ARROW) {
        save("descending-arcs_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
        print("SVG Downloaded");
        noLoop();
    }

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<hr>

## Description

Oscillating arcs flow down the page, decreasing in width.

## Instructions

Refresh the page to regenerate the sketch. Press the Left Arrow key to save an SVG.

## Code Sample

```JavaScript
    noFill();
    let polar = 1;
    let shrink = 0;

    for(let y_pos = 0; y_pos < height; y_pos += 50) {
        for(let x_pos = 0; x_pos < width; x_pos += 25) {
            if (polar === 1) {
                arc(x_pos, y_pos, 100 - shrink, 50, HALF_PI, PI + HALF_PI);
            } else {
                arc(x_pos, y_pos, 100 - shrink, 50, PI + HALF_PI, TAU + HALF_PI);
            }
        }
        polar *= -1;
        shrink += 5;
    }
```
## Thoughts

I really like how this turned out. It has a little bit of an [M. C. Esher](https://www.nga.gov/features/slideshows/mc-escher-life-and-work.html#slide_1) vibe.
