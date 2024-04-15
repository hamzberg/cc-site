+++
title = "Rising Arrows"
weight = 5
+++

<!-- Load the Styling -->
<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Rising Arrows
 * Author:  hamzberg
 * Version: 0.1
 * Date:    15 April 2024
 *
 * Notes:
 *   -
 */

class Wave {

    constructor(x_Position, y_Position, scale) {

        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.scale = scale;

    }

    update() {

        this.y_Position += random([6, 8, 12]);

        if(this.y_Position > height) {

            this.y_Position = random(-height, -height - 800);
            this.x_Position = random(50, width - 50);

        }

    }

    display() {

        noStroke();

        fill('yellow');

        push();

            translate(this.x_Position, -this.y_Position);

            scale(this.scale);

            beginShape();
                vertex(50, 0);
                vertex(100, 50);
                vertex(50, 25);
                vertex(0, 50);
            endShape(CLOSE);

        pop();

    }

}

const waves = [];

let save_Seq = false;
let frame_Count = 10;

/** Sketch Begin **/

function setup() {

    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');

    for(let i = 0; i < 50; i++) {
        waves.push(
            new Wave(
                random(0, width),
                random(0, height),
                random(.5, 1)
            )
        );
    }

}

function draw() {

    /* Needed to refresh every new frame. */
    clear();

    /* Creative code here. */

    for(let i = 0; i < waves.length; i++) {

        waves[i].display();
        waves[i].update();

    }

    ////////////////////////

    /* Manages sequential saving */
    if (save_Seq && (frame_Count > 0)) {

        save("rising-arrows_frame" + frame_Count + ".svg");
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

A collection of random generated arrowhead rise to the top of the canvas.

## Instructions

To save a set of frames, enter your desired amount in the number field and press the "Save Sequential" button.

## Code Sample

```javascript
class Wave {
    constructor(x_Position, y_Position, scale) {
        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.scale = scale;
    }
    update() {
        this.y_Position += random([6, 8, 12]);
        if(this.y_Position > height) {
            this.y_Position = random(-height, -height - 800);
            this.x_Position = random(50, width - 50);
        }
    }
    display() {
        noStroke();
        fill('yellow');
        push();
            translate(this.x_Position, -this.y_Position);
            scale(this.scale);
            beginShape();
                vertex(50, 0);
                vertex(100, 50);
                vertex(50, 25);
                vertex(0, 50);
            endShape(CLOSE);
        pop();
    }
}
const waves = [];
function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
    for(let i = 0; i < 50; i++) {
        waves.push(
            new Wave(
                random(0, width),
                random(0, height),
                random(.5, 1)
            )
        );
    }
}
function draw() {
    clear();
    for(let i = 0; i < waves.length; i++) {
        waves[i].display();
        waves[i].update();
    }
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

None recorded.
