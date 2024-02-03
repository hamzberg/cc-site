+++
title = "p5JS DOM Test"
weight = 1
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
 * Title:   Processing Sketch No. #
 * Author:  hamzberg
 * Version: 0.0
 * Date:    15 January 2024
 *
 * Notes:
 *   -
 */

let fuse = true;

function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
}

function draw() {

    //clear();

    fill('red');
    noStroke();

    if(fuse == true){

        rect(random(0, width), random(0, height), 100, 100);

        fuse = false;

    }

}

function fuseTrigger() {

    clear();
    fuse = true;

}

function exportSVG() {

    save("p5js-dom-test_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
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

This experiment uses the HTML DOM to interact with the sketch.

## Instructions

Press the "Regenerate" button to regenerate the sketch. Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```HTML
<script>

let fuse = true;

function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
}

function draw() {
    fill('red');
    noStroke();

    if(fuse == true){
        rect(random(0, width), random(0, height), 100, 100);
        fuse = false;
    }
}

function fuseTrigger() {
    clear();
    fuse = true;
}

function exportSVG() {
    save("p5js-dom-test_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
    print("SVG Downloaded");
}

</script>

<button onclick="fuseTrigger()"> Regenerate </button>

<button onclick="exportSVG()"> Save SVG </button>
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I thought I had to use p5.js' [Instance Mode](https://github.com/processing/p5.js/wiki/Global-and-instance-mode) in order to get this to work
but then realized that I could just use the HTML DOM since the sketch is in "Global Mode."
