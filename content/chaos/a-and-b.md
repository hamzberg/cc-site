+++
title = "A and B"
weight = 1
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   A and B
 * Author:  hamzberg
 * Version: 0.1
 * Date:    6 January 2024
 *
 * Description:
 *   -
 */

function setup() {
    let c = createCanvas(600, 600, SVG);
    c.parent('processing-canvas');

    background(64, 24, 53); // Blackberry Black

    noStroke();

    let color_Palette = [
        color(242, 61, 109), // Lipstick Pink
        color(140, 42, 96),  // Maroon Purple
        color(50, 166, 166), // Turquoise
        color(217, 136, 89), // Golden Brown
    ];

    for (let i = 0; i < 100; i += 1) {

        fill(random(color_Palette));

        shapeA(random(0, width), random(0, height), random(.1, .5));
        shapeB(random(1, width), random(0, height), random(.1, .5));

    }

}

function shapeA(x_pos, y_pos, scale) {

    x_pos /= scale;
    y_pos /= scale;

    beginShape();
        vertex((25 + x_pos) * scale, (0 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (0 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (25 + y_pos) * scale);
        vertex((100 + x_pos) * scale, (25 + y_pos) * scale);
        vertex((100 + x_pos) * scale, (125 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (125 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (125 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (125 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (50 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (50 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (25 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (25 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (0 + y_pos) * scale);
    endShape(CLOSE);

}

function shapeB(x_pos, y_pos, scale) {

    x_pos /= scale;
    y_pos /= scale;

    beginShape();
        vertex((0 + x_pos) * scale, (0 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (0 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (75 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (75 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((100 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((100 + x_pos) * scale, (150 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (150 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (175 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (175 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (150 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (150 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (175 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (175 + y_pos) * scale);
    endShape(CLOSE);

}

function draw() {

    exportSVG();

}

function exportSVG() {

    if (keyCode === LEFT_ARROW) {
        save("a-and-b_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
        print("SVG Downloaded");
        noLoop();
    }

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<hr>

## Description

Pixel-stylized letters of 'a' and 'b' randomly generate in different sizes and positions on the canvas.

## Instructions

Refresh the page to regenerate the sketch. Press the Left Arrow key to save an SVG.

## Code Sample

```JavaScript
function setup() {
    background(64, 24, 53); // Blackberry Black
    noStroke();

    let color_Palette = [
        color(242, 61, 109), // Lipstick Pink
        color(140, 42, 96),  // Maroon Purple
        color(50, 166, 166), // Turquoise
        color(217, 136, 89), // Golden Brown
    ];

    for (let i = 0; i < 100; i += 1) {
        fill(random(color_Palette));
        shapeA(random(0, width), random(0, height), random(.1, .5));
        shapeB(random(1, width), random(0, height), random(.1, .5));
    }
}

function shapeA(x_pos, y_pos, scale) {

    x_pos /= scale;
    y_pos /= scale;

    beginShape();
        vertex((25 + x_pos) * scale, (0 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (0 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (25 + y_pos) * scale);
        vertex((100 + x_pos) * scale, (25 + y_pos) * scale);
        vertex((100 + x_pos) * scale, (125 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (125 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (125 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (125 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (50 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (50 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (25 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (25 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (0 + y_pos) * scale);
    endShape(CLOSE);

}

function shapeB(x_pos, y_pos, scale) {

    x_pos /= scale;
    y_pos /= scale;

    beginShape();
        vertex((0 + x_pos) * scale, (0 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (0 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (75 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (75 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((100 + x_pos) * scale, (100 + y_pos) * scale);
        vertex((100 + x_pos) * scale, (150 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (150 + y_pos) * scale);
        vertex((75 + x_pos) * scale, (175 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (175 + y_pos) * scale);
        vertex((50 + x_pos) * scale, (150 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (150 + y_pos) * scale);
        vertex((25 + x_pos) * scale, (175 + y_pos) * scale);
        vertex((0 + x_pos) * scale, (175 + y_pos) * scale);
    endShape(CLOSE);

}
```
## Thoughts

p5js' vertex functions are fun to use.
