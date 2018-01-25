# **Finding Lane Lines on the Road** 

## Lane finding Writeup 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect my work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Description of my pipeline. 

My pipeline consisted of 5 steps. 
1. Convert the images to grayscale.
2. Create a blur image using gaussian blue from gray scaled image.
3. Canny edge detection for detecting the edge. 
4. Define a region of interest(ROI) 
5. Apply Hough transform to detect lanes.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...
1. seperating left and right lines using slope of the line.
2. average of the points of the line and slope for each right and left side lines.

As one point and slope is enoguh to exterpolate the final lane/line, and y0 is equals to image.shape[0]
the folloing line eqation can be used to exterpolate the lane marking :
x1 = x0 + (1/slope)*(y1-y0)

### 2. Potential shortcomings 
The parameters (e.g., kernel size, line_gap) are hard coded. This might create problem for different types of images having different color scheme and contrast.


### 3.Possible improvements 
These parameters can be fined tuned to get an optimal level so that it can detect lanes in all types of image. 


