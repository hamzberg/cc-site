+++
title = "Simplicity Grid"
weight = 13
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Simplicity Grid
 * Author:  hamzberg
 * Version: 0.0
 * Date:    20 January 2024
 *
 * Notes:
 *   -
 */

let fuse = true;

function setup() {
    let c = createCanvas(500, 500, SVG);
    c.parent('processing-canvas');
    noStroke();
}

function draw() {

    if(fuse == true){

        for(let x_Position = 0; x_Position < width; x_Position += 50){

            for(let y_Position = 0; y_Position < height; y_Position += 50){

                switch(random([1, 2, 3, 4, 5])) {
                    case 1:
                        fill(217, 4, 22);
                        break;
                    case 2:
                        fill(242, 145, 199);
                        break;
                    case 3:
                        fill(4, 217, 139);
                        break;
                    case 4:
                        fill(242, 226, 5);
                        break;
                    case 5:
                        fill(242, 183, 5);
                        break;
                }

                switch(random([1,2,3,4])) {
                    case 1:
                        makeQuarterCircle(x_Position, y_Position, 1);
                        break;
                    case 2:
                        makeDiamond(x_Position, y_Position, 1);
                        break;
                    case 3:
                        circle(25 + x_Position, 25 + y_Position, 50);
                        break;
                    case 4:
                        square(0 + x_Position, 0 + y_Position, 50);
                        break;

                }

            }

        }

        fuse = false;

    }

}

function makeQuarterCircle(x_Position, y_Position, scale) {
    beginShape();
        vertex(50 + x_Position, 0 + y_Position);
        vertex(50 + x_Position, 50 + y_Position);
        vertex(0 + x_Position, 50 + y_Position);
        bezierVertex(0 + x_Position, 50 + y_Position,
                     0 + x_Position, 0 + y_Position,
                     50 + x_Position, 0 + y_Position);
    endShape(CLOSE);
}

function makeDiamond(x_Position, y_Position, scale) {
    beginShape();
        vertex(25 + x_Position, 0 + y_Position);
        vertex(50 + x_Position, 25 + y_Position);
        vertex(25 + x_Position, 50 + y_Position);
        vertex(0 + x_Position, 25 + y_Position);
    endShape(CLOSE);
}

function fuseTrigger() {

    clear();
    fuse = true;

}

function exportSVG() {

    save("simplicity-grid_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
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

Generates a grid of colorful shapes.

## Instructions

Press the "Regenerate" button to regenerate the sketch. Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```JavaScript
function setup() {
    noStroke();
}

function draw() {
    for(let x_Position = 0; x_Position < width; x_Position += 50){
        for(let y_Position = 0; y_Position < height; y_Position += 50){
            switch(random([1, 2, 3, 4, 5])) {
                case 1:
                    fill(217, 4, 22);
                    break;
                case 2:
                    fill(242, 145, 199);
                    break;
                case 3:
                    fill(4, 217, 139);
                    break;
                case 4:
                    fill(242, 226, 5);
                    break;
                case 5:
                    fill(242, 183, 5);
                    break;
            }
            switch(random([1,2,3,4])) {
                case 1:
                    makeQuarterCircle(x_Position, y_Position, 1);
                    break;
                case 2:
                    makeDiamond(x_Position, y_Position, 1);
                    break;
                case 3:
                    circle(25 + x_Position, 25 + y_Position, 50);
                    break;
                case 4:
                    square(0 + x_Position, 0 + y_Position, 50);
                    break;
            }
        }
    }
}

function makeQuarterCircle(x_Position, y_Position, scale) {
    beginShape();
        vertex(50 + x_Position, 0 + y_Position);
        vertex(50 + x_Position, 50 + y_Position);
        vertex(0 + x_Position, 50 + y_Position);
        bezierVertex(0 + x_Position, 50 + y_Position,
                     0 + x_Position, 0 + y_Position,
                     50 + x_Position, 0 + y_Position);
    endShape(CLOSE);
}

function makeDiamond(x_Position, y_Position, scale) {
    beginShape();
        vertex(25 + x_Position, 0 + y_Position);
        vertex(50 + x_Position, 25 + y_Position);
        vertex(25 + x_Position, 50 + y_Position);
        vertex(0 + x_Position, 25 + y_Position);
    endShape(CLOSE);
}
```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I used this one with POSCA Markers. Turned out pretty neat!
