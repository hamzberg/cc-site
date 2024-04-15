+++
title = "Green Stars"
weight = 3
+++

<!-- Load the Styling -->
<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Green Stars
 * Author:  hamzberg
 * Version: 0.1
 * Date:    15 April 2024
 *
 * Notes:
 *   -
 */

class Star {

    constructor(x_Position, y_Position, scale, rotation) {
        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.scale = scale;
        this.rotation = rotation;
    }

    update() {

        this.x_Position += 12;

        if (this.x_Position > 650) {

            this.x_Position = random(-100, -700);
            this.y_Position = random(0, 600);

        }

    }

    display() {
        noStroke();
        fill('green');

        push(); // Save the current transformation state

        translate(this.x_Position, this.y_Position);

        rotate(this.rotation);

        scale(this.scale);

        beginShape();
            vertex(25, 0);
            bezierVertex(25, 0, 25, 25, 50, 25);
            vertex(50, 25);
            bezierVertex(50, 25, 25, 25, 25, 50);
            vertex(25, 50);
            bezierVertex(25, 50, 25, 25, 0, 25);
            vertex(0, 25);
            bezierVertex(0, 25, 25, 25, 25, 0);
        endShape(CLOSE);

        pop();
    }
}

let stars = [];

let save_Seq = false;
let frame_Count = 10;

/** Sketch Begin **/

function setup() {
    let c = createCanvas(600, 600, SVG);
    c.parent('processing-canvas');

    for(let i = 0; i < 35; i++) {
        stars.push(
            new Star(
                random(0, width + width/2),
                random(100, height),
                random(0.25, 1),
                random(PI, PI/2)
            )
        );
    }

}

function draw() {

    /* Needed to refresh every new frame. */
    clear();

    /* Creative code here. */

    for (let i = 0; i < stars.length; i++) {
        stars[i].display();
        stars[i].update();
    }

    ////////////////////////

    /* Manages sequential saving */
    if (save_Seq && (frame_Count > 0)) {

        save("green-stars_frame" + frame_Count + ".svg");
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

Green stars of varying size and rotations fly by from left to right.

## Instructions

To save a set of frames, enter your desired amount in the number field and press the "Save Sequential" button.

## Code Sample

```javascript
class Star {
    constructor(x_Position, y_Position, scale, rotation) {
        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.scale = scale;
        this.rotation = rotation;
    }
    update() {
        this.x_Position += 12;
        if (this.x_Position > 650) {
            this.x_Position = random(-100, -700);
            this.y_Position = random(0, 600);
        }
    }
    display() {
        noStroke();
        fill('green');
        push();
            translate(this.x_Position, this.y_Position);
            rotate(this.rotation);
            scale(this.scale);
            beginShape();
                vertex(25, 0);
                bezierVertex(25, 0, 25, 25, 50, 25);
                vertex(50, 25);
                bezierVertex(50, 25, 25, 25, 25, 50);
                vertex(25, 50);
                bezierVertex(25, 50, 25, 25, 0, 25);
                vertex(0, 25);
                bezierVertex(0, 25, 25, 25, 25, 0);
            endShape(CLOSE);
        pop();
    }
}
let stars = [];
function setup() {
    let c = createCanvas(600, 600, SVG);
    c.parent('processing-canvas');
    for(let i = 0; i < 35; i++) {
        stars.push(
            new Star(
                random(0, width + width/2),
                random(100, height),
                random(0.25, 1),
                random(PI, PI/2)
            )
        );
    }
}
function draw() {
    clear();
    for (let i = 0; i < stars.length; i++) {
        stars[i].display();
        stars[i].update();
    }
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

None recorded.
