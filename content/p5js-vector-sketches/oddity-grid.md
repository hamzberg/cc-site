+++
title = "Oddity Grid"
weight = 12
+++

<style>

#dom-gui {

    display: flex;
    justify-content: center;
    gap: 1rem;

}

button {

    padding: 1rem;
    cursor: pointer;

    background: #A9FDAC;

    border-radius: .5rem;

    outline: none;
    border: none;

    transition-duration: 0.2s;

    width: 100%;

    box-shadow: 0 4px #32A287;

}

button:hover {

    background: #DFFFC7;

}

button:active {

    background: #32A287;

    transform: translateY(4px);

}

</style>

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Oddity Grid
 * Author:  hamzberg
 * Version: 0.1
 * Date:    19 January 2024
 *
 * Notes:
 *   -
 */

let fuse = true;

function setup() {
    let c = createCanvas(600, 600, SVG);
    c.parent('processing-canvas');
    noFill();
}

function draw() {

    if(fuse == true){

        let scale = 50;

        for (let x_Position = 0; x_Position < width; x_Position += scale) {
            for (let y_Position = 0; y_Position < height; y_Position += scale) {

                switch(random([1, 2, 3, 4])) {
                    case 1:
                        makeTileOne(x_Position, y_Position, 1);
                        break;
                    case 2:
                        makeTileTwo(x_Position, y_Position, 1);
                        break;
                    case 3:
                        makeTileThree(x_Position, y_Position, 1);
                        break;
                    case 4:
                        makeTileFour(x_Position, y_Position, 1);
                        break;
                }
            }
        }

        fuse = false;

    }

}

function makeTileOne(x_Position, y_Position, scale) {

    x_Position /= scale;
    y_Position /= scale;

    // Vertical
    line((10 + x_Position) * scale, (0 + y_Position) * scale,
         (10 + x_Position) * scale, (50 + y_Position) * scale);
    line((20 + x_Position) * scale, (0 + y_Position) * scale,
         (20 + x_Position) * scale, (50 + y_Position) * scale);
    line((30 + x_Position) * scale, (0 + y_Position) * scale,
         (30 + x_Position) * scale, (50 + y_Position) * scale);
    line((40 + x_Position) * scale, (0 + y_Position) * scale,
         (40 + x_Position) * scale, (50 + y_Position) * scale);
    line((50 + x_Position) * scale, (0 + y_Position) * scale,
         (50 + x_Position) * scale, (50 + y_Position) * scale);

    // Horizontal
    line((0 + x_Position) * scale, (10 + y_Position) * scale,
         (50 + x_Position) * scale, (10 + y_Position) * scale);
    line((0 + x_Position) * scale, (20 + y_Position) * scale,
         (50 + x_Position) * scale, (20 + y_Position) * scale);
    line((0 + x_Position) * scale, (30 + y_Position) * scale,
         (50 + x_Position) * scale, (30 + y_Position) * scale);
    line((0 + x_Position) * scale, (40 + y_Position) * scale,
         (50 + x_Position) * scale, (40 + y_Position) * scale);
    line((0 + x_Position) * scale, (50 + y_Position) * scale,
         (50 + x_Position) * scale, (50 + y_Position) * scale);

}

function makeTileTwo(x_Position, y_Position, scale) {

    x_Position /= scale;
    y_Position /= scale;

    for(let x_Position_Local = 5; x_Position_Local <= 50; x_Position_Local += 10){
        for(let y_Position_Local = 5; y_Position_Local <= 50; y_Position_Local += 10){
            circle((x_Position_Local + x_Position) * scale, (y_Position_Local + y_Position) * scale, 10);
        }
    }

}

function makeTileThree(x_Position, y_Position, scale){

    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 100, 100, PI, PI + HALF_PI, OPEN);
    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 80, 80, PI, PI + HALF_PI, OPEN);
    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 60, 60, PI, PI + HALF_PI, OPEN);
    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 40, 40, PI, PI + HALF_PI, OPEN);
    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 20, 20, PI, PI + HALF_PI, OPEN);

}

function makeTileFour(x_Position, y_Position, scale) {

    x_Position /= scale;
    y_Position /= scale;

    // Vertical
    line((5 + x_Position) * scale, (0 + y_Position) * scale,
         (5 + x_Position) * scale, (50 + y_Position) * scale);
    line((10 + x_Position) * scale, (0 + y_Position) * scale,
         (10 + x_Position) * scale, (50 + y_Position) * scale);
    line((15 + x_Position) * scale, (0 + y_Position) * scale,
         (15 + x_Position) * scale, (50 + y_Position) * scale);
    line((20 + x_Position) * scale, (0 + y_Position) * scale,
         (20 + x_Position) * scale, (50 + y_Position) * scale);
    line((25 + x_Position) * scale, (0 + y_Position) * scale,
         (25 + x_Position) * scale, (50 + y_Position) * scale);
    line((30 + x_Position) * scale, (0 + y_Position) * scale,
         (30 + x_Position) * scale, (50 + y_Position) * scale);
    line((35 + x_Position) * scale, (0 + y_Position) * scale,
         (35 + x_Position) * scale, (50 + y_Position) * scale);
    line((40 + x_Position) * scale, (0 + y_Position) * scale,
         (40 + x_Position) * scale, (50 + y_Position) * scale);
    line((45 + x_Position) * scale, (0 + y_Position) * scale,
         (45 + x_Position) * scale, (50 + y_Position) * scale);
    line((50 + x_Position) * scale, (0 + y_Position) * scale,
         (50 + x_Position) * scale, (50 + y_Position) * scale);

    // Horizontal
    line((0 + x_Position) * scale, (5 + y_Position) * scale,
         (50 + x_Position) * scale, (5 + y_Position) * scale);
    line((0 + x_Position) * scale, (10 + y_Position) * scale,
         (50 + x_Position) * scale, (10 + y_Position) * scale);
    line((0 + x_Position) * scale, (15 + y_Position) * scale,
         (50 + x_Position) * scale, (15 + y_Position) * scale);
    line((0 + x_Position) * scale, (20 + y_Position) * scale,
         (50 + x_Position) * scale, (20 + y_Position) * scale);
    line((0 + x_Position) * scale, (25 + y_Position) * scale,
         (50 + x_Position) * scale, (25 + y_Position) * scale);
    line((0 + x_Position) * scale, (30 + y_Position) * scale,
         (50 + x_Position) * scale, (30 + y_Position) * scale);
    line((0 + x_Position) * scale, (35 + y_Position) * scale,
         (50 + x_Position) * scale, (35 + y_Position) * scale);
    line((0 + x_Position) * scale, (40 + y_Position) * scale,
         (50 + x_Position) * scale, (40 + y_Position) * scale);
    line((0 + x_Position) * scale, (45 + y_Position) * scale,
         (50 + x_Position) * scale, (45 + y_Position) * scale);
    line((0 + x_Position) * scale, (50 + y_Position) * scale,
         (50 + x_Position) * scale, (50 + y_Position) * scale);

}

function fuseTrigger() {

    clear();
    fuse = true;

}

function exportSVG() {

    save("oddity-grid_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
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

Generates a grid of pictographs from a set of tiles.

## Instructions

Press the "Regenerate" button to regenerate the sketch. Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```JavaScript
function setup() {
    noFill();
}

function draw() {

        let scale = 50;

        for (let x_Position = 0; x_Position < width; x_Position += scale) {
            for (let y_Position = 0; y_Position < height; y_Position += scale) {
               switch(random([1, 2, 3, 4])) {
                    case 1:
                        makeTileOne(x_Position, y_Position, 1);
                        break;
                    case 2:
                        makeTileTwo(x_Position, y_Position, 1);
                        break;
                    case 3:
                        makeTileThree(x_Position, y_Position, 1);
                        break;
                    case 4:
                        makeTileFour(x_Position, y_Position, 1);
                        break;
               }
          }
     }
}

function makeTileOne(x_Position, y_Position, scale) {

    x_Position /= scale;
    y_Position /= scale;

    // Vertical
    line((10 + x_Position) * scale, (0 + y_Position) * scale,
         (10 + x_Position) * scale, (50 + y_Position) * scale);
    line((20 + x_Position) * scale, (0 + y_Position) * scale,
         (20 + x_Position) * scale, (50 + y_Position) * scale);
    line((30 + x_Position) * scale, (0 + y_Position) * scale,
         (30 + x_Position) * scale, (50 + y_Position) * scale);
    line((40 + x_Position) * scale, (0 + y_Position) * scale,
         (40 + x_Position) * scale, (50 + y_Position) * scale);
    line((50 + x_Position) * scale, (0 + y_Position) * scale,
         (50 + x_Position) * scale, (50 + y_Position) * scale);

    // Horizontal
    line((0 + x_Position) * scale, (10 + y_Position) * scale,
         (50 + x_Position) * scale, (10 + y_Position) * scale);
    line((0 + x_Position) * scale, (20 + y_Position) * scale,
         (50 + x_Position) * scale, (20 + y_Position) * scale);
    line((0 + x_Position) * scale, (30 + y_Position) * scale,
         (50 + x_Position) * scale, (30 + y_Position) * scale);
    line((0 + x_Position) * scale, (40 + y_Position) * scale,
         (50 + x_Position) * scale, (40 + y_Position) * scale);
    line((0 + x_Position) * scale, (50 + y_Position) * scale,
         (50 + x_Position) * scale, (50 + y_Position) * scale);

}

function makeTileTwo(x_Position, y_Position, scale) {

    x_Position /= scale;
    y_Position /= scale;

    for(let x_Position_Local = 5; x_Position_Local <= 50; x_Position_Local += 10){
        for(let y_Position_Local = 5; y_Position_Local <= 50; y_Position_Local += 10){
            circle((x_Position_Local + x_Position) * scale, (y_Position_Local + y_Position) * scale, 10);
        }
    }

}

function makeTileThree(x_Position, y_Position, scale){

    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 100, 100, PI, PI + HALF_PI, OPEN);
    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 80, 80, PI, PI + HALF_PI, OPEN);
    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 60, 60, PI, PI + HALF_PI, OPEN);
    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 40, 40, PI, PI + HALF_PI, OPEN);
    arc((50 + x_Position) * scale, (50 + y_Position) * scale, 20, 20, PI, PI + HALF_PI, OPEN);

}

function makeTileFour(x_Position, y_Position, scale) {

    x_Position /= scale;
    y_Position /= scale;

    // Vertical
    line((5 + x_Position) * scale, (0 + y_Position) * scale,
         (5 + x_Position) * scale, (50 + y_Position) * scale);
    line((10 + x_Position) * scale, (0 + y_Position) * scale,
         (10 + x_Position) * scale, (50 + y_Position) * scale);
    line((15 + x_Position) * scale, (0 + y_Position) * scale,
         (15 + x_Position) * scale, (50 + y_Position) * scale);
    line((20 + x_Position) * scale, (0 + y_Position) * scale,
         (20 + x_Position) * scale, (50 + y_Position) * scale);
    line((25 + x_Position) * scale, (0 + y_Position) * scale,
         (25 + x_Position) * scale, (50 + y_Position) * scale);
    line((30 + x_Position) * scale, (0 + y_Position) * scale,
         (30 + x_Position) * scale, (50 + y_Position) * scale);
    line((35 + x_Position) * scale, (0 + y_Position) * scale,
         (35 + x_Position) * scale, (50 + y_Position) * scale);
    line((40 + x_Position) * scale, (0 + y_Position) * scale,
         (40 + x_Position) * scale, (50 + y_Position) * scale);
    line((45 + x_Position) * scale, (0 + y_Position) * scale,
         (45 + x_Position) * scale, (50 + y_Position) * scale);
    line((50 + x_Position) * scale, (0 + y_Position) * scale,
         (50 + x_Position) * scale, (50 + y_Position) * scale);

    // Horizontal
    line((0 + x_Position) * scale, (5 + y_Position) * scale,
         (50 + x_Position) * scale, (5 + y_Position) * scale);
    line((0 + x_Position) * scale, (10 + y_Position) * scale,
         (50 + x_Position) * scale, (10 + y_Position) * scale);
    line((0 + x_Position) * scale, (15 + y_Position) * scale,
         (50 + x_Position) * scale, (15 + y_Position) * scale);
    line((0 + x_Position) * scale, (20 + y_Position) * scale,
         (50 + x_Position) * scale, (20 + y_Position) * scale);
    line((0 + x_Position) * scale, (25 + y_Position) * scale,
         (50 + x_Position) * scale, (25 + y_Position) * scale);
    line((0 + x_Position) * scale, (30 + y_Position) * scale,
         (50 + x_Position) * scale, (30 + y_Position) * scale);
    line((0 + x_Position) * scale, (35 + y_Position) * scale,
         (50 + x_Position) * scale, (35 + y_Position) * scale);
    line((0 + x_Position) * scale, (40 + y_Position) * scale,
         (50 + x_Position) * scale, (40 + y_Position) * scale);
    line((0 + x_Position) * scale, (45 + y_Position) * scale,
         (50 + x_Position) * scale, (45 + y_Position) * scale);
    line((0 + x_Position) * scale, (50 + y_Position) * scale,
         (50 + x_Position) * scale, (50 + y_Position) * scale);

}
```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

Yeah, I could've condensed these functions with for loops.
