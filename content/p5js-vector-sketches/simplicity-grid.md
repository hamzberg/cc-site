+++
title = "Simplicity Grid"
weight = 11
+++

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

<button onclick="fuseTrigger()"> Regenerate </button>

<button onclick="exportSVG()"> Save SVG </button>

<hr>

## Description

This page contains code to be used with starting a new creative code project.

## Instructions

Copy the contents of this Markdown file to a new sketch. Remember to change the SVG download file name.

## Code Sample

```JavaScript
let fuse = true;

function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
}

function draw() {
    if(fuse == true){
        fuse = false;
    }
}

function fuseTrigger() {
    clear();
    fuse = true;
}

function exportSVG() {
    save("temp_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
    print("SVG Downloaded");
}
```
## Thoughts

"Head empty."
