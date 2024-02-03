+++
title = "Descending Arcs"
weight = 6
+++

<style>

#dom-gui {

    display: flex;
    justify-content: center;
    gap: 1rem;

}

button {

    padding: 1rem;
    cursor: pointer;

    background: #A9FDAC;

    border-radius: .5rem;

    outline: none;
    border: none;

    transition-duration: 0.2s;

    width: 100%;

    box-shadow: 0 4px #32A287;

}

button:hover {

    background: #DFFFC7;

}

button:active {

    background: #32A287;

    transform: translateY(4px);

}

</style>

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Descending Arcs
 * Author:  hamzberg
 * Version: 0.2
 * Date:    6 January 2024
 *
 * Description:
 *   -
 */

let fuse = true;

function setup() {
    let c = createCanvas(600, 800, SVG);
    c.parent('processing-canvas');

    noFill();

}

function draw() {

    if(fuse == true){

        let polar = 1;

        let shrink = 0;

        for(let y_pos = 0; y_pos < height; y_pos += 50) {

            for(let x_pos = 0; x_pos < width; x_pos += 25) {

                if (polar === 1) {
                    arc(x_pos, y_pos, 100 - shrink, 50, HALF_PI, PI + HALF_PI);
                } else {
                    arc(x_pos, y_pos, 100 - shrink, 50, PI + HALF_PI, TAU + HALF_PI);
                }

            }

            polar *= -1;

            shrink += 5;
        }

        fuse = false;
    }

}

function exportSVG() {

    save("descending-arcs_" + day() + "-" + month() + "-" + year() + "_" + millis() + ".svg");
    print("SVG Downloaded");

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<div id="dom-gui">
    <button onclick="exportSVG()"> Save SVG </button>
</div>

<hr>

## Description

Oscillating arcs flow down the page, decreasing in width.

## Instructions

Press the "Save SVG" button to save the sketch as an SVG.

## Code Sample

```JavaScript
    noFill();
    let polar = 1;
    let shrink = 0;

    for(let y_pos = 0; y_pos < height; y_pos += 50) {
        for(let x_pos = 0; x_pos < width; x_pos += 25) {
            if (polar === 1) {
                arc(x_pos, y_pos, 100 - shrink, 50, HALF_PI, PI + HALF_PI);
            } else {
                arc(x_pos, y_pos, 100 - shrink, 50, PI + HALF_PI, TAU + HALF_PI);
            }
        }
        polar *= -1;
        shrink += 5;
    }
```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

I really like how this turned out. It has a little bit of an [M. C. Esher](https://www.nga.gov/features/slideshows/mc-escher-life-and-work.html#slide_1) vibe.
