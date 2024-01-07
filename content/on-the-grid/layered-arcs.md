+++
title = "Layered Arcs"
weight = 2
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Layered Arcs
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

        for(let y_pos = 0; y_pos < height; y_pos += 50) {

        for(let x_pos = 0; x_pos < width; x_pos += 50) {

            arc(x_pos, y_pos, 100, 100, HALF_PI, PI + HALF_PI);

        }

    }

}


function draw() {

    exportSVG();

}

function exportSVG() {

    if (keyCode === LEFT_ARROW) {
        save("mySVG.svg");
        print("SVG Downloaded");
        noLoop();
    }

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<hr>

## Description

Arcs are layered on top of each other in a geometric hill like pattern.

## Instructions

Refresh the page to regenerate the sketch. Press the Left Arrow key to save an SVG.

## Code Sample

```JavaScript
    noFill();

    for(let y_pos = 0; y_pos < height; y_pos += 50) {
        for(let x_pos = 0; x_pos < width; x_pos += 50) {
            arc(x_pos, y_pos, 100, 100, HALF_PI, PI + HALF_PI);
        }
    }
```
## Thoughts

I wanted to try something different. I don't usually work with arcs.
