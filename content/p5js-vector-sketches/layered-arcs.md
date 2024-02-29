+++
title = "Layered Arcs"
weight = 4
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Layered Arcs
 * Author:  hamzberg
 * Version: 0.2
 * Date:    6 January 2024
 *
 * Description:
 *   -
 */

let fuse = true;

function setup() {
    let c = createCanvas(600, 800, SVG);
    c.parent('processing-canvas');

    noFill();

}

function draw() {

    if(fuse == true){

        for(let y_pos = 0; y_pos < height; y_pos += 50) {

            for(let x_pos = 0; x_pos < width; x_pos += 50) {

                arc(x_pos, y_pos, 100, 100, HALF_PI, PI + HALF_PI);

            }

        }

        fuse = false;
    }

}

function exportSVG() {

    save("layered-arcs_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
    print("SVG Downloaded");

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<div id="dom-gui">
    <button onclick="exportSVG()"> Save SVG </button>
</div>

<hr>

## Description

Arcs are layered on top of each other in a geometric hill-like pattern.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```JavaScript
    noFill();

    for(let y_pos = 0; y_pos < height; y_pos += 50) {
        for(let x_pos = 0; x_pos < width; x_pos += 50) {
            arc(x_pos, y_pos, 100, 100, HALF_PI, PI + HALF_PI);
        }
    }
```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I wanted to try something different. I don't usually work with arcs.
