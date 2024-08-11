
# Adobe Gensolve

**Objective** : Our mission is to identify, regularize, and beautify curves in 2D Euclideanspace. We’ll start by focusing on closed curves and progressively work with more complex shapes. This project will also cover symmetry and curve completion techniques.

**Problem 1 :** Identify & regularize shapes

**Problem 2 :** Exploring Symmetery in Shapes

**Problem 3 :** Completing Incomplete Curves

# Our Solution :

### Regularization & Identification : 
**Hyper simplification of our thought process :** 
Imagine you have a bunch of points on a piece of paper, and you want to reshape these points to fit into a nice, neat shape, like a rectangle with rounded corners or a perfectly regular polygon (like a hexagon or a pentagon). The goal of this code is to take these scattered points and organize them into these more regular, pleasing shapes.
#### For Rectangles and other regular polygons 

 * Find boundaries 
 * Calculate Dimensions
 * Calculate where to place the regular corners
 

#### For Polygons (Made of line segments)

 * Find the center
 * Calculate Size of the figure
    * With the center and size determined, we then "place" the vertices of our polygon evenly around the circle. We calculate the angles between each vertex so that they’re all equally spaced.
 * Evenly space the vertices , with center and size determined this is easy to do, then place the vertices where required

#### For Ellipses and Circles 

 * Fitting an ellipse requires at least five points, so we made a function that check this and proceeds accordingly
 * Calculate Dimensions using EllipseModel from skimage.measure

### Identification and regularization of irregular Shapes as Ellipse/ circle, rectangle or star 
 * Compute the convex hull of the points, which is the smallest polygon that can enclose all the points.
 * Calculate metrics like the area, perimeter, and compactness of the hull to help identify the shape.
 * Compare these metrics against known thresholds to classify the shape as a circle, rectangle, star, or unknown.

#### Use of Bexier Curves 
 Why bezier Curves? 

Bezier curves are useful for predicting shapes because they provide a flexible and smooth way to approximate complex curves and shapes with a relatively simple mathematical representation.

#### Working?

* take input
* use spline (spline is a smooth, flexible curve that approximates the input points based on a parameterization)
* Generate new points

### Finding Symmetry

We copy the given shape and flip it over in different ways, straight up and down, side to side, or diagonally. Then, it compares the original shape to the flipped copies. If parts of the shape match up when you flip it, it might be symmetrical. This helps you understand the symmetry of the shape better.


### Use of RDP Algorithm
The Ramer-Douglas-Peucker algorithm, also known as the Douglas-Peucker algorithm or iterative end-point fit algorithm, is a method for simplifying a curve composed of line segments to a similar curve with fewer points.
It's particularly useful for reducing the number of points in a digital map while preserving its general shape.


In order to analyse and complete the incomplete the curves we reduce the number of points needed to represent a path while maintaining its overall shape within a certain tolerance. This is useful for compressing data, improving processing efficiency and noise reduction. However,here it is aminly for efficiency and compression.




