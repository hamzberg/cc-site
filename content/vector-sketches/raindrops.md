+++
title = "Raindrops"
weight = 8
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Raindrops
 * Author:  hamzberg
 * Version: 0.1
 * Date:    15 January 2024
 *
 * Notes:
 *   -
 */

let fuse = true;

function setup() {

    let c = createCanvas(600, 600, SVG);
    c.parent('processing-canvas');
    noStroke();

}

function draw() {

    if(fuse == true) {

        for(let i = 0; i < 100; i += 1) {

            fill(
                random([
                    color(63, 137, 166), // Dark Blue
                    color(154, 199, 217) // Light Blue
                ]));

            dropMaker(random(0, width), (Math.log(i) * 100), .5);

        }

        fuse = false;

    }

    exportSVG();
    //GUI();

}

function dropMaker(x_Pos, y_Pos, scale) {

    x_Pos /= scale;
    y_Pos /= scale;

    beginShape();
        vertex((25 + x_Pos) * scale, (0 + y_Pos) * scale);
        bezierVertex((25 + x_Pos) * scale, (25 + y_Pos) * scale,
                     (50 + x_Pos) * scale, (50 + y_Pos) * scale,
                     (50 + x_Pos) * scale, (75 + y_Pos) * scale);
        bezierVertex((50 + x_Pos) * scale, (100 + y_Pos) * scale,
                     (15 + x_Pos) * scale, (125 + y_Pos) * scale,
                     (0 + x_Pos) * scale,  (75 + y_Pos) * scale);
        bezierVertex((0 + x_Pos) * scale,  (50 + y_Pos) * scale,
                     (25 + x_Pos) * scale, (50 + y_Pos) * scale,
                     (25 + x_Pos) * scale, (0 + y_Pos) * scale);
        vertex((25 + x_Pos) * scale, (0 + x_Pos) * scale);
    endShape(CLOSE);

}

function exportSVG() {

    if (keyCode === LEFT_ARROW) {
        save("raindrops_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
        print("SVG Downloaded");
        noLoop();
    }

}

function GUI() {

    let gen = createButton('Generate');
    gen.position(400, 400);

    gen.mousePressed(() => {
        clear();
        fuse = true;
    });

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<hr>

## Description

Raindrops are placed randomly based on the log of the first for loop times 100.

## Instructions

Refresh the page to regenerate the sketch. Press the Left Arrow key to save an SVG.

## Code Sample

```JavaScript
let fuse = true;

function setup() {
    noStroke();
}

function draw() {
    if(fuse == true) {
        for(let i = 0; i < 100; i += 1) {
            fill(random([color(63, 137, 166), color(154, 199, 217)]));
            dropMaker(random(0, width), (Math.log(i) * 100), .5);
        }
        fuse = false;
    }
}

function dropMaker(x_Pos, y_Pos, scale) {
    x_Pos /= scale;
    y_Pos /= scale;
    beginShape();
        vertex((25 + x_Pos) * scale, (0 + y_Pos) * scale);
        bezierVertex((25 + x_Pos) * scale, (25 + y_Pos) * scale,
                     (50 + x_Pos) * scale, (50 + y_Pos) * scale,
                     (50 + x_Pos) * scale, (75 + y_Pos) * scale);
        bezierVertex((50 + x_Pos) * scale, (100 + y_Pos) * scale,
                     (15 + x_Pos) * scale, (125 + y_Pos) * scale,
                     (0 + x_Pos) * scale,  (75 + y_Pos) * scale);
        bezierVertex((0 + x_Pos) * scale,  (50 + y_Pos) * scale,
                     (25 + x_Pos) * scale, (50 + y_Pos) * scale,
                     (25 + x_Pos) * scale, (0 + y_Pos) * scale);
        vertex((25 + x_Pos) * scale, (0 + x_Pos) * scale);
    endShape(CLOSE);
}
```

## Thoughts

Wanted to play with bezier curves. There's a weird vertex that isn't visible on every raindrop that causes a line to appear on the axidraw, but it looks cool.
