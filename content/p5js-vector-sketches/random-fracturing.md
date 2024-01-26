+++
title = "Random Fracturing"
weight = 1
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Random Fracturing
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

    noStroke();
    fill('red');

    for(let x_pos = 0; x_pos < 1000; x_pos += 10) {

        for(let y_pos = 0; y_pos < 1000; y_pos +=10) {

            rect(x_pos, y_pos, random(0, 15), random(0, 15));

        }

    }

}


function draw() {

    exportSVG();

}

function exportSVG() {

    if (keyCode === LEFT_ARROW) {
        save("random-fracturing_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
        print("SVG Downloaded");
        noLoop();
    }

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<hr>

## Description

This page contains code to be used with starting a new creative code project.

## Instructions

Copy the contents of this Markdown file to a new sketch. Remember to change the SVG download file name.

## Code Sample

```JavaScript
    noStroke();
    fill('red');

    for(let x_pos = 0; x_pos < 1000; x_pos += 10) {
        for(let y_pos = 0; y_pos < 1000; y_pos +=10) {
            rect(x_pos, y_pos, random(0, 15), random(0, 15));
        }
    }
```
## Thoughts

I have no idea what I'm doing :^)
