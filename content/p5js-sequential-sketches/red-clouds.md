+++
title = "Red Clouds"
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
 * Title:   Red Clouds
 * Author:  hamzberg
 * Version: 0.1
 * Date:    15 April 2024
 *
 * Notes:
 *   -
 */

class Cloud {

    constructor(x_Position, y_Position, scale) {

        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.scale = scale;

    }

    update() {

        this.x_Position -= 8;

        if(this.x_Position < -width/2) {

            this.x_Position = random(width, width*2);
            this.y_Position = random(50, height - 50);

        }

    }

    display() {

        noStroke();

        fill('red');

        push();

            translate(this.x_Position, this.y_Position);

            scale(1.5, this.scale);

            beginShape();
                vertex(0, 75);
                bezierVertex(0, 75, 15, 20, 25, 50);
                vertex(25, 50);
                bezierVertex(25, 50, 35, 0, 50, 50);
                vertex(50, 50);
                bezierVertex(50, 50, 65, 20, 75, 75);
                vertex(75, 75);
                bezierVertex(75, 75, 75, 105, 50, 100);
                vertex(50, 100);
                bezierVertex(50, 100, 35, 125, 25, 100);
                vertex(25, 100);
                bezierVertex(25, 100, 15, 105, 0, 75);
            endShape(CLOSE);

        pop();

    }

}

const clouds = [];

let save_Seq = false;
let frame_Count = 10;

/** Sketch Begin **/

function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');

    for(let i = 0; i < 20; i++) {
        clouds.push(
            new Cloud(
                random(0, height),
                random(0, width*2),
                random(.25, .75)
            )
        );
    }

}

function draw() {

    /* Needed to refresh every new frame. */
    clear();

    /* Creative code here. */

    for(let i = 0; i < clouds.length; i++) {

        clouds[i].display();
        clouds[i].update();

    }

    ////////////////////////

    /* Manages sequential saving */
    if (save_Seq && (frame_Count > 0)) {

        save("red-clouds_frame" + frame_Count + ".svg");
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

Primative-looking red clouds pass by from the right to the left.

## Instructions

To save a set of frames, enter your desired amount in the number field and press the "Save Sequential" button.

## Code Sample

```javascript
class Cloud {
    constructor(x_Position, y_Position, scale) {
        this.x_Position = x_Position;
        this.y_Position = y_Position;
        this.scale = scale;
    }
    update() {
        this.x_Position -= 8;
        if(this.x_Position < -width/2) {
            this.x_Position = random(width, width*2);
            this.y_Position = random(50, height - 50);
        }
    }
    display() {
        noStroke();
        fill('red');
        push();
            translate(this.x_Position, this.y_Position);
            scale(1.5, this.scale);
            beginShape();
                vertex(0, 75);
                bezierVertex(0, 75, 15, 20, 25, 50);
                vertex(25, 50);
                bezierVertex(25, 50, 35, 0, 50, 50);
                vertex(50, 50);
                bezierVertex(50, 50, 65, 20, 75, 75);
                vertex(75, 75);
                bezierVertex(75, 75, 75, 105, 50, 100);
                vertex(50, 100);
                bezierVertex(50, 100, 35, 125, 25, 100);
                vertex(25, 100);
                bezierVertex(25, 100, 15, 105, 0, 75);
            endShape(CLOSE);
        pop();
    }
}
const clouds = [];
function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
    for(let i = 0; i < 20; i++) {
        clouds.push(
            new Cloud(
                random(0, height),
                random(0, width*2),
                random(.25, .75)
            )
        );
    }
}
function draw() {
    clear();
    for(let i = 0; i < clouds.length; i++) {
        clouds[i].display();
        clouds[i].update();
    }
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

None recorded.
