+++
title = "Eye Spiral"
weight = 9
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Eye Spiral
 * Author:  hamzberg
 * Version: 0.2
 * Date:    7 January 2024
 *
 * Notes:
 *   -
 */

let fuse = true;

function setup() {
    let c = createCanvas(700, 700, SVG);
    c.parent('processing-canvas');

    noFill();
    strokeWeight(1);

}

function makeSplash() {

    beginShape();
        curveVertex(25, 25);
        curveVertex(100, 75);
        curveVertex(125, 25);
        curveVertex(150, 75);
        curveVertex(200, 0);
        curveVertex(175, 150);
        curveVertex(250, 225);
        curveVertex(150, 200);
        curveVertex(50, 250);
        curveVertex(100, 175);
        curveVertex(25, 125);
        curveVertex(75, 100);
    endShape(CLOSE);

}

function draw() {

    if(fuse == true){

        for(let i = 0; i < 100; i += 1) {

            stroke(
                random([
                    color(242, 227, 179), // light
                    color(159, 145, 119), // medium
                    color(122, 84, 71)    // dark
                    ]));
            push();
            translate(width / 2, height / 2);
            rotate(1 + (i * 5));
            makeSplash();
            pop();
        }

        fuse = false;
    }

}

function exportSVG() {

    save("eye-spiral_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
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

A blob shape is cloned and rotated around the center of the canvas, creating a wacky spiral.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```JavaScript
function setup() {
    background(1, 35, 64);

    noFill();
    strokeWeight(1);

    for(let i = 0; i < 100; i += 1) {

        stroke(
            random([
                color(242, 227, 179), // light
                color(159, 145, 119), // medium
                color(122, 84, 71)    // dark
                ]));
        push();
        translate(width / 2, height / 2);
        rotate(1 + (i * 5));
        makeSplash();
        pop();
    }

}

function makeSplash() {

    beginShape();
        curveVertex(25, 25);
        curveVertex(100, 75);
        curveVertex(125, 25);
        curveVertex(150, 75);
        curveVertex(200, 0);
        curveVertex(175, 150);
        curveVertex(250, 225);
        curveVertex(150, 200);
        curveVertex(50, 250);
        curveVertex(100, 175);
        curveVertex(25, 125);
        curveVertex(75, 100);
    endShape(CLOSE);

}
```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I was looking at some other pen-plot artists and got inspired to really playing with lines. Turned out pretty well.
