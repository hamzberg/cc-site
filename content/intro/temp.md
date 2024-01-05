+++
title = "Template"
weight = 1
+++

<!-- Load the Library -->
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.min.js"></script>
<script type = "text/javascript" src = "../../scripts/libs/p5js/p5.svg.js"></script>

<!-- Load the Sketch -->
<script>

/*
 * Title:   Processing Sketch No. #
 * Author:  hamzberg
 * Version: 0.0
 * Date:    11 December 2024
 *
 * Description:
 *   -
 */

function setup() {
    let c = createCanvas(600, 300, SVG);
    c.parent('processing-canvas');
}


function draw() {

    exportSVG();

}

function exportSVG() {

    if (keyCode === LEFT_ARROW) {
        save("mySVG.svg");
        print("SVG Downloaded");
        noLoop();
    }

}

</script>

<!-- Insert the Sketch -->
<div id="processing-canvas"></div>

This page contains code to be used with starting a new creative code project.
