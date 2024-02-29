+++
title = "Zag Walkers"
weight = 11
+++

<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Zag Walkers
 * Author:  hamzberg
 * Version: 0.1
 * Date:    16 January 2024
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

        for(let i = 0; i < 50; i += 1){
            drawLine();
        }

        fuse = false;

    }

}

function drawLine() {

    let x_Pos = 0;
    let y_Pos = 0;

    if (document.getElementById("radio_Random").checked == true) {
        x_Pos = random(0, width);
    } else {
        x_Pos = width/2;
    }

    beginShape();
        vertex(x_Pos, y_Pos);
        for(let i = 0; i < 150; i += 1){
            vertex(x_Pos += random([-5, 5]), y_Pos += 5);
        }
    endShape();

}


function fuseTrigger() {

    clear();
    fuse = true;

}

function exportSVG() {

    save("zag-walkers_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
    print("SVG Downloaded");

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<div id="dom-gui">
    <button onclick="fuseTrigger()"> Regenerate </button>
    <button onclick="exportSVG()"> Save SVG </button>
</div>

<br>

Select Mode:
<input type="radio" id="radio_Random" name="select_Pos" value="Random">
    <label for="random"> Random </label>
<input type="radio" id="radio_Center" name="select_Pos" value="Center" checked="checked">
    <label for="center"> Center </label>

<hr>

## Description

Generates several walkers with their left or right turn based on random polarity as they move down the canvas.

## Instructions

Press the "Regenerate" button to regenerate the sketch. Press the "Save SVG" button to save the sketch as an SVG. Select between "Random" and "Center" modes for different effects.

## Code Sample

```JavaScript
let fuse = true;

function setup() {
    noFill();
}

function draw() {
    if(fuse == true){
        for(let i = 0; i < 50; i += 1){
            drawLine();
        }
        fuse = false;
    }
}

function drawLine() {
    let x_Pos = 0;
    let y_Pos = 0;

    if (document.getElementById("radio_Random").checked == true) {
        x_Pos = random(0, width);
    } else {
        x_Pos = width/2;
    }

    beginShape();
        vertex(x_Pos, y_Pos);
        for(let i = 0; i < 150; i += 1){
            vertex(x_Pos += random([-5, 5]), y_Pos += 5);
        }
    endShape();
}

```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

Wanted to play with the HTML DOM more and picked an easy sketch idea to make it.
