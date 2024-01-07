+++
title = "Hello Rectangle!"
weight = 1
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Hello Rectangle
 * Author:  hamzberg
 * Version: 0.1
 * Date:    29 September 2023
 *
 * Description:
 *   -
 */

function setup() {
  let c = createCanvas(700, 300);
  c.parent('processing-canvas');

  noStroke();
}

function draw() {
    fill("black");
    rect(50,50,100,200);

    fill("red");
    rect(250,100,300,100);
}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<hr>

## Description

A vertical black rectangle and horizontal red rectangle rest on the canvas.

## Instructions

"At ease, soldier."

## Code Sample

```JavaScript
    fill("black");
    rect(50,50,100,200);

    fill("red");
    rect(250,100,300,100);
```
## Thoughts

Obligatory greeting of the omnipresent rectangles.
