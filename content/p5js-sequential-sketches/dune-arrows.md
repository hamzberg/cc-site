+++
title = "Dune Arrows"
weight = 1
+++

<!-- Load the Styling -->
<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Dune Arrows
 * Author:  hamzberg
 * Version: 0.1
 * Date:    15 April 2024
 *
 * Notes:
 *   -
 */

class Waves {

    constructor(x_Pos, y_Pos, scale) {

        this.scale = scale;
        this.x_Pos = (x_Pos / this.scale);
        this.y_Pos = (y_Pos / this.scale);

    }

    display() {

        noStroke();
        fill('yellow');

        for(let i = 25; i <= 100; i += 25) {

            let scale_Mod = i / 25;

            beginShape();
                vertex(
                    (40 + this.x_Pos + i) * (this.scale / scale_Mod),
                    (0 + this.y_Pos) * (this.scale / scale_Mod)
                    );
                vertex(
                    (25 + this.x_Pos + i) * (this.scale / scale_Mod),
                    (25 + this.y_Pos) * (this.scale / scale_Mod)
                    );
                vertex(
                    (40 + this.x_Pos + i) * (this.scale / scale_Mod),
                    (50 + this.y_Pos) * (this.scale / scale_Mod)
                    );
                vertex(
                    (0 + this.x_Pos + i) * (this.scale / scale_Mod),
                    (25 + this.y_Pos) * (this.scale / scale_Mod)
                    );
            endShape(CLOSE);

        }

    }

    move() {

        if (this.x_Pos <= (-1000 * this.scale)) {
            this.x_Pos = 3600 + this.scale;
        }

        this.x_Pos -= random([5, 10, 15]);

    }

}

const some_Waves = [50];

let save_Seq = false;
let frame_Count = 10;

/** Sketch Begin **/

function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');

    for (let i = 0; i < 50; i += 1) {
        some_Waves[i] = new Waves(random(width, width*10), random(0, height), 1);
    }

}

function draw() {

    /* Needed to refresh every new frame. */
    clear();

    /* Creative code here. */

    translate(width/2, 0);

    for (let i = 0; i < some_Waves.length; i += 1) {

        some_Waves[i].display();
        some_Waves[i].move();

    }

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

A bunch of yellow arrowheads go from right to left in a swarm.

## Instructions

To save a set of frames, enter your desired amount in the number field and press the "Save Sequential" button.

## Code Sample

```javascript
class Waves {
    constructor(x_Pos, y_Pos, scale) {
        this.scale = scale;
        this.x_Pos = (x_Pos / this.scale);
        this.y_Pos = (y_Pos / this.scale);
    }
    display() {
        noStroke();
        fill('yellow');
        for(let i = 25; i <= 100; i += 25) {
            let scale_Mod = i / 25;
            beginShape();
                vertex(
                    (40 + this.x_Pos + i) * (this.scale / scale_Mod),
                    (0 + this.y_Pos) * (this.scale / scale_Mod)
                    );
                vertex(
                    (25 + this.x_Pos + i) * (this.scale / scale_Mod),
                    (25 + this.y_Pos) * (this.scale / scale_Mod)
                    );
                vertex(
                    (40 + this.x_Pos + i) * (this.scale / scale_Mod),
                    (50 + this.y_Pos) * (this.scale / scale_Mod)
                    );
                vertex(
                    (0 + this.x_Pos + i) * (this.scale / scale_Mod),
                    (25 + this.y_Pos) * (this.scale / scale_Mod)
                    );
            endShape(CLOSE);
        }
    }
    move() {
        if (this.x_Pos <= (-1000 * this.scale)) {
            this.x_Pos = 3600 + this.scale;
        }
        this.x_Pos -= random([5, 10, 15]);
    }
}
const some_Waves = [50];
function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
    for (let i = 0; i < 50; i += 1) {
        some_Waves[i] = new Waves(random(width, width*10), random(0, height), 1);
    }
}
function draw() {
    clear();
    translate(width/2, 0);
    for (let i = 0; i < some_Waves.length; i += 1) {
        some_Waves[i].display();
        some_Waves[i].move();
    }
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

None recorded.
