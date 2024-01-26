+++
title = "Inward Arcs"
weight = 3
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Inward Arcs
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

    for(let y_pos = 0; y_pos < height; y_pos += 50) {

        for(let x_pos = 0; x_pos < width; x_pos += 50) {

            if (polar === 1) {
                arc(x_pos, y_pos, 100, 100, HALF_PI, PI + HALF_PI);
            } else {
                arc(x_pos, y_pos, 100, 100, PI + HALF_PI, TAU + HALF_PI);
                arc(x_pos + 10, y_pos, 100, 100, PI + HALF_PI, TAU + HALF_PI);
            }

        }

        polar *= -1;

    }

}


function draw() {

    exportSVG();

}

function exportSVG() {

    if (keyCode === LEFT_ARROW) {
        save("inward-arcs_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
        print("SVG Downloaded");
        noLoop();
    }

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<hr>

## Description

Arcs cut into each other as the pattern descends on the canvas.

## Instructions

Refresh the page to regenerate the sketch. Press the Left Arrow key to save an SVG.

## Code Sample

```JavaScript
    noFill();
    let polar = 1;

    for(let y_pos = 0; y_pos < height; y_pos += 50) {
        for(let x_pos = 0; x_pos < width; x_pos += 50) {
            if (polar === 1) {
                arc(x_pos, y_pos, 100, 100, HALF_PI, PI + HALF_PI);
            } else {
                arc(x_pos, y_pos, 100, 100, PI + HALF_PI, TAU + HALF_PI);
                arc(x_pos + 10, y_pos, 100, 100, PI + HALF_PI, TAU + HALF_PI);
            }
        }
        polar *= -1;
    }
```

## Thoughts

Thought this looked pretty cool after adding a polarizing variable.
