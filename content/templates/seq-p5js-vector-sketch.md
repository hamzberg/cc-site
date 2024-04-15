+++
title = "new"
weight = 4
+++

<!-- Load the Styling -->
<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Processing Sketch No. #
 * Author:  hamzberg
 * Version: 0.0
 * Date:    1 December 2024
 *
 * Notes:
 *   -
 */

class obj {

    constructor() {

    }

    update() {

    }

}

let save_Seq = false;
let frame_Count = 10;

/** Sketch Begin **/

function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
}

function draw() {

    /* Needed to refresh every new frame. */
    clear();

    /* Creative code here. */

    ////////////////////////

    /* Manages sequential saving */
    if (save_Seq && (frame_Count > 0)) {

        save("temp_frame" + frame_Count + ".svg");
        frame_Count -= 1;

    } else if (frame_Count <= 0 ) {

        save_Seq = false;

    }

}

function exportSeq() {

    frame_Count = document.getElementById("frameCountField").value;
    save_Seq = true;

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<div id="dom-gui">
    <input type="number" id="frameCountField" value="10" min="1" max="99">
    <button onclick="exportSeq()"> Save Sequential </button>
</div>

<hr>

## Description

This page contains code to be used with starting a new creative code project.

## Instructions

Copy the contents of this Markdown file to a new sketch. Remember to change the SVG download file name.

## Code Sample

```javascript

```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

"Head empty."
