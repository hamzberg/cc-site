+++
title = "Basic Data Types"
weight = 1
+++

## Description

Presented is a code sample of what was learned from the PaperJS data types tutorial.

## Code Sample

``` javascript
var point_A = new Point(10, 10);
console.log("point_A's value is " + point_A);

var path_A = new Path();
path_A.add(point_A);
console.log("path_A's value is " + path_A);

point_A.y = point_A.x + 10;
console.log("point_A's new value is " + point_A);

var point_B = new Point(20, 40);
console.log("point_B's value is " + point_B);

point_B.y = point_B.x * 4;
console.log("point_B's new value is " + point_B);

var point_C = new Point(30, 60);
var point_D = new Point(point_C);
console.log("point_C's value is " + point_C);
console.log("point_D's value is the same as point_C's value: " + point_D);

var point_E = new Point(70, 80);
var point_F = point_E;

point_F.y = 20;

console.log("point_E's value was modifed because it's a reference to point_F, so: " + point_E);

// Size

var size_A = new Size();
console.log("size_A was initialized with no values therefore: " + size_A);

size_A.width = 10;
size_A.height = size_A.width + 10;
console.log("size_A's new value is " + size_A);

// Rectangle

var rect_A = new Rectangle(point_A, size_A);
console.log("rect_A's value is " + rect_A);

var rect_B = new Rectangle(20, 30, 80, 90);
console.log("rect_B's value is " + rect_B);

var rect_C = new Rectangle(point_A, point_B);
console.log("rect_C was constructed using to points. The value is " + rect_C);

var rect_D = new Rectangle(new Point(100, 200), new Point(200, 300));
console.log("rect_D's value is " + rect_D);
```

## Thoughts

Paper.js utilizes some interesting concepts for its datatypes. Having come from a Java and Java-based Processing background, learning JavaScript and this library has already led to a different way of thinking.

Notably, I find myself seeing the <code>point</code> datatype as the start of everything.

