+++
title = "Sequential Frame Test"
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
 * Version: 0.1
 * Date:    27 March 2024
 *
 * Notes:
 *   -
 */

class sq {

    constructor(x_Position, y_Position, size) {

        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.size = size;

    }

    update() {

        noStroke();
        fill('green');
        square(this.x_Position, this.y_Position, this.size);

    }

}

const SQ_ONE = new sq(0, 50, 50);
const SQ_TOO = new sq(0, 100, 50);
const SQ_TRE = new sq(0, 150, 50);
const SQ_FOR = new sq(0, 200, 50);

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
    if (SQ_ONE.x_Position > width) { SQ_ONE.x_Position = -SQ_ONE.size; }

    SQ_ONE.update();
    SQ_ONE.x_Position += 5;

    if (SQ_TOO.x_Position > width) { SQ_TOO.x_Position = -SQ_TOO.size; }

    SQ_TOO.update();
    SQ_TOO.x_Position += 10;

    if (SQ_TRE.x_Position > width) { SQ_TRE.x_Position = -SQ_TRE.size; }

    SQ_TRE.update();
    SQ_TRE.x_Position += 15;

    if (SQ_FOR.x_Position > width) { SQ_FOR.x_Position = -SQ_FOR.size; }

    SQ_FOR.update();
    SQ_FOR.x_Position += 20;

    /* Manages sequential saving */
    if (save_Seq && (frame_Count > 0)) {

        save("sequential-frame-test_frame" + frame_Count + ".svg");
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

This is a test to save sequential frames from a p5js creative code sketch.

## Instructions

To save a set of frames, enter your desired amount in the number field and press the "Save Sequential" button.

## Code Sample

```javascript
class sq {
    constructor(x_Position, y_Position, size) {
        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.size = size;
    }
    update() {
        noStroke();
        fill('green');
        square(this.x_Position, this.y_Position, this.size);
    }
}
const SQ_ONE = new sq(0, 50, 50);
const SQ_TOO = new sq(0, 100, 50);
const SQ_TRE = new sq(0, 150, 50);
const SQ_FOR = new sq(0, 200, 50);
function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
}
function draw() {
    clear();
    if (SQ_ONE.x_Position > width) { SQ_ONE.x_Position = -SQ_ONE.size; }
    SQ_ONE.update();
    SQ_ONE.x_Position += 5;
    if (SQ_TOO.x_Position > width) { SQ_TOO.x_Position = -SQ_TOO.size; }
    SQ_TOO.update();
    SQ_TOO.x_Position += 10;
    if (SQ_TRE.x_Position > width) { SQ_TRE.x_Position = -SQ_TRE.size; }
    SQ_TRE.update();
    SQ_TRE.x_Position += 15;
    if (SQ_FOR.x_Position > width) { SQ_FOR.x_Position = -SQ_FOR.size; }
    SQ_FOR.update();
    SQ_FOR.x_Position += 20;
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I'm not sure if Object Oriented Programming is required to do sequential sketches, but nonetheless this implementation does.
