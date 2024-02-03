+++
title = "A and B"
weight = 8
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
 * Title:   A and B
 * Author:  hamzberg
 * Version: 0.2
 * Date:    6 January 2024
 *
 * Description:
 *   -
 */

let fuse = true;

function setup() {
    let c = createCanvas(600, 600, SVG);
    c.parent('processing-canvas');

    noStroke();

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

    if(fuse == true){

        background(64, 24, 53); // Blackberry Black

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

        fuse = false;

    }

}

function fuseTrigger() {

    clear();
    fuse = true;

}

function exportSVG() {

    save("a-and-b_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
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

Pixel-stylized letters of 'a' and 'b' randomly generate in different sizes and positions on the canvas.

## Instructions

Press the "Regenerate" button to regenerate the sketch. Press the "Save SVG" button to save the sketch as an SVG.

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
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

p5js' vertex functions are fun to use.
