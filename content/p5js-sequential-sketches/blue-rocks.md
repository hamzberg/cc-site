+++
title = "Blue Rocks"
weight = 2
+++

<!-- Load the Styling -->
<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Blue Rocks
 * Author:  hamzberg
 * Version: 0.1
 * Date:    15 April 2024
 *
 * Notes:
 *   -
 */

class Rock {

    constructor(x_Position, y_Position, scale, rotation) {

        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.scale = scale;
        this.rotation = rotation;

    }

    update() {

        this.y_Position -= 12;

        if(this.y_Position < -height) {

            this.y_Position = random(height, height + height);
            this.x_Position = random(50, width - 50);

        }

    }

    display() {

        noStroke();

        fill('blue');

        push();

            translate(this.x_Position, -this.y_Position);

            scale(this.scale);

            rotate(this.rotation);

            beginShape();
                vertex(0, 25);
                vertex(100, 0);
                vertex(125, 75);
                vertex(50, 100);
                vertex(0, 50);
            endShape(CLOSE);

        pop();

    }

}

const rocks = [];

let save_Seq = false;
let frame_Count = 10;

/** Sketch Begin **/

function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');

    for(let i = 0; i < 20; i++) {
        rocks.push(
            new Rock(
                random(0, width),
                random(0, height + height),
                random(.25, .75),
                random(0.1, 1)
            )
        );
    }

}

function draw() {

    /* Needed to refresh every new frame. */
    clear();

    /* Creative code here. */

    for(let i = 0; i < rocks.length; i++) {

        rocks[i].display();
        rocks[i].update();

    }

    ////////////////////////

    /* Manages sequential saving */
    if (save_Seq && (frame_Count > 0)) {

        save("blue-rocks_frame" + frame_Count + ".svg");
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

A bunch of blue rocks fall from the top of the canvas past the bottom.

## Instructions

To save a set of frames, enter your desired amount in the number field and press the "Save Sequential" button.

## Code Sample

```javascript
class Rock {
    constructor(x_Position, y_Position, scale, rotation) {
        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.scale = scale;
        this.rotation = rotation;
    }
    update() {
        this.y_Position -= 12;
        if(this.y_Position < -height) {
            this.y_Position = random(height, height + height);
            this.x_Position = random(50, width - 50);
        }
    }
    display() {
        noStroke();
        fill('blue');
        push();
            translate(this.x_Position, -this.y_Position);
            scale(this.scale);
            rotate(this.rotation);
            beginShape();
                vertex(0, 25);
                vertex(100, 0);
                vertex(125, 75);
                vertex(50, 100);
                vertex(0, 50);
            endShape(CLOSE);
        pop();
    }
}
const rocks = [];
function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
    for(let i = 0; i < 20; i++) {
        rocks.push(
            new Rock(
                random(0, width),
                random(0, height + height),
                random(.25, .75),
                random(0.1, 1)
            )
        );
    }
}
function draw() {
    clear();
    for(let i = 0; i < rocks.length; i++) {
        rocks[i].display();
        rocks[i].update();
    }
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

None recorded.
