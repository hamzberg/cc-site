+++
title = "Deluge"
weight = 14
+++

<!-- Load the Styling -->
<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Deluge
 * Author:  hamzberg
 * Version: 0.1
 * Date:    28 February 2024
 *
 * Notes:
 *   -
 */

let fuse = true;

function setup() {
    let c = createCanvas(600, 400, SVG);
    c.parent('processing-canvas');

    noFill();

}

function draw() {

    if(fuse == true){

        let x_Position = 0;
        let y_Position = 0;
        let scale = 0;

        //line(0, height - 100, width, height - 100);

        for(let i = 0; i < 250; i += 1){

            x_Position = random(-50, width + 50);
            y_Position = random(-50, height + 50);
            scale = random(0, 50);

            if (y_Position < height) {

                line(x_Position, y_Position,
                     x_Position - (50 - scale), y_Position - (50 - scale));

            }

            if (y_Position > height - 75) {

                if (i % 2 == 0) {

                arc(x_Position, y_Position, 30, 10,
                    PI + HALF_PI + (QUARTER_PI * 1.5),
                    PI*2 + HALF_PI * 2 + (QUARTER_PI / 2));

                }

            }

        }

        fuse = false;

    }

}

function fuseTrigger() {

    clear();
    fuse = true;

}

function exportSVG() {

    save("deluge_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
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

Generates a deluge-like effect.

## Instructions

Press the "Regenerate" button to regenerate the sketch. Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```javascript
function setup() {
    let c = createCanvas(600, 400, SVG);
    c.parent('processing-canvas');
    noFill();
}
function draw() {
    if(fuse == true){
        let x_Position = 0;
        let y_Position = 0;
        let scale = 0;
        for(let i = 0; i < 250; i += 1){
            x_Position = random(-50, width + 50);
            y_Position = random(-50, height + 50);
            scale = random(0, 50);
            if (y_Position < height) {
                line(x_Position, y_Position,
                     x_Position - (50 - scale), y_Position - (50 - scale));
            }
            if (y_Position > height - 75) {
                if (i % 2 == 0) {
                arc(x_Position, y_Position, 30, 10,
                    PI + HALF_PI + (QUARTER_PI * 1.5),
                    PI*2 + HALF_PI * 2 + (QUARTER_PI / 2));
                }
            }
        }
    }
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

Works pretty well for rain.
