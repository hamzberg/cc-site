+++
title = "Red Mist"
weight = 3
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Red Mist
 * Author:  hamzberg
 * Version: 0.2
 * Date:    22 December 2023
 *
 * Notes:
 *   -
 */

class dot {

  constructor(x_pos, y_pos, size) {

    this.x_pos = x_pos | 0;

    this.y_pos = y_pos | 0;

    this.size = size | 0;

  }

  blue_mode() {

    noStroke();

    fill('blue');

    ellipse(this.x_pos, this.y_pos, this.size);

  }

  red_mode() {

    noStroke();

    fill('red');

    ellipse(this.x_pos, this.y_pos, this.size);

  }

}

function setup() {

    frameRate(5);

    let c = createCanvas(700, 300);

    c.parent('processing-canvas');
}

function draw() {
  background(255);

  let dot_one = new dot(240, 240, 50);
  dot_one.blue_mode();

  let dot_too = new dot(140, 140, 150);
  dot_too.red_mode();

  for(let i = 0; i < 100; i+=1 ) {

    new dot(random(0, width), random(0, height), random(1, 100)).red_mode();

  }
}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

<hr>

## Description

Uses a custom 'dot' object to create a loop of 100 dots of different sizes placed randomly in the canvas. Based on the lecture by [Bernat Ferragut](https://ga-course.surge.sh/).

## Instructions

"There is nothing that we can do."

## Code Sample

```JavaScript
class dot {
  constructor(x_pos, y_pos, size) {
    this.x_pos = x_pos | 0;
    this.y_pos = y_pos | 0;
    this.size = size | 0;
  }

  blue_mode() {
    noStroke();
    fill('blue');
    ellipse(this.x_pos, this.y_pos, this.size);
  }

  red_mode() {
    noStroke();
    fill('red');
    ellipse(this.x_pos, this.y_pos, this.size);
  }
}

function setup() {
    frameRate(5);
}

function draw() {
  background(220);

  let dot_one = new dot(240, 240, 50);
  dot_one.blue_mode();

  let dot_too = new dot(140, 140, 150);
  dot_too.red_mode();

  for(let i = 0; i < 100; i+=1 ) {
    new dot(random(0, width), random(0, height), random(1, 100)).red_mode();
  }
}
```
The full script for this sketch can be found on [Github](https://github.com/hamzberg/cc-site).

## Thoughts

This helped me understand Object Oriented Programming better.
