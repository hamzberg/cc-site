+++
title = "Exes, Ohhs, and Arrows"
weight = 15
+++

<!-- Load the Styling -->
<link rel="stylesheet" href="/styles/style.css" />

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Exes, Ohhs, and Arrows
 * Author:  hamzberg
 * Version: 0.1
 * Date:    21 March 2024
 *
 * Notes:
 *   -
 */

let fuse = true;

function setup() {
    let c = createCanvas(600, 600, SVG);
    c.parent('processing-canvas');
    strokeWeight(5);
    noFill();
}

function draw() {

    if(fuse == true){

        for(let x_Position = 0; x_Position < width; x_Position += 12) {

            for(let y_Position = 0; y_Position < height; y_Position += 12) {

                switch(random([1, 2, 3, 4])) {
                    case 1:
                        // Rich Black
                        stroke(12, 15, 10);
                        break;
                    case 2:
                        // Magenta
                        stroke(255, 32, 110);
                        break;
                    case 3:
                        // Yellow
                        stroke(251, 255, 18);
                        break;
                    case 4:
                        // Teal
                        stroke(65, 234, 212);
                        break;
                    default:
                        stroke(0);
                }

                push();
                    translate(width/2, height/2);
                    rotate(random(1, 15));

                    switch(random([1, 2, 3])) {
                        case 1:
                            line(10 + x_Position, 0 + y_Position, 10 + x_Position, 20 + y_Position);
                            line(0 + x_Position, 10 + y_Position, 20 + x_Position, 10 + y_Position);
                            break;
                        case 2:
                            circle(x_Position, y_Position, 20);
                            break;
                        case 3:
                            // left diagonal
                            line(5 + x_Position, 5 + y_Position, 10 + x_Position, 0 + y_Position);
                            // right diagonal
                            line(15 + x_Position, 5 + y_Position, 10 + x_Position, 0 + y_Position);
                            // vertical
                            line(10 + x_Position, 0 + y_Position, 10 + x_Position, 15 + y_Position);
                        default:
                            console.log("womp womp");
                    }
                pop();

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

    save("exes-ohhs-and-arrows_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
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

Generates a mess of exes, ohhs, and arrows.

## Instructions

Press the "Regenerate" button to regenerate the sketch. Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```javascript
function setup() {
    let c = createCanvas(600, 600, SVG);
    c.parent('processing-canvas');
    strokeWeight(5);
    noFill();
}
function draw() {
    if(fuse == true){
        for(let x_Position = 0; x_Position < width; x_Position += 12) {
            for(let y_Position = 0; y_Position < height; y_Position += 12) {
                switch(random([1, 2, 3, 4])) {
                    case 1:
                        stroke(12, 15, 10);
                        break;
                    case 2:
                        stroke(255, 32, 110);
                        break;
                    case 3:
                        stroke(251, 255, 18);
                        break;
                    case 4:
                        stroke(65, 234, 212);
                        break;
                    default:
                        stroke(0);
                }
                push();
                    translate(width/2, height/2);
                    rotate(random(1, 15));
                    switch(random([1, 2, 3])) {
                        case 1:
                            line(10 + x_Position, 0 + y_Position, 10 + x_Position, 20 + y_Position);
                            line(0 + x_Position, 10 + y_Position, 20 + x_Position, 10 + y_Position);
                            break;
                        case 2:
                            circle(x_Position, y_Position, 20);
                            break;
                        case 3:
                            line(5 + x_Position, 5 + y_Position, 10 + x_Position, 0 + y_Position);
                            line(15 + x_Position, 5 + y_Position, 10 + x_Position, 0 + y_Position);
                            line(10 + x_Position, 0 + y_Position, 10 + x_Position, 15 + y_Position);
                        default:
                            console.log("womp womp");
                    }
                pop();
            }
        }
    }
}
```

The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

Really nice pattern for some gift wrapping paper.
