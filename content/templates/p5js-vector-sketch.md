+++
title = "p5JS Vector Sketch"
weight = 1
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Processing Sketch No. #
 * Author:  hamzberg
 * Version: 0.0
 * Date:    11 December 2024
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

## Code Source

The code for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

"Head empty."
