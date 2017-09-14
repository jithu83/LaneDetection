# **Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Try it on images and videos and see if it works


[//]: # (Image References)

[image1]: ./capture.png

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of the following steps
* Gray scale
* Gaussian Blur
* Canny edge detection
* Masking to region of interest (Lane lines)
* Hough Transform to find the lane lines
* Averaging the lane lines
* Super-imposing to output

Look at the image to see the details of each step.

I added get_aggr_lanelines() to average the list of lines returned by Hough Transform to 2 lines, each showing each lane. The left and right lane lines were separated using +ve and -ve slope and averaged separately. The section titled *Line averaging and classification* has the details. The classic line equation $y = mx + c$ was used in solving line i.e converting a pair of points to  **slope** and **intercept**.

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

Some potential issues:
* In curvy winding roads, averaging to lines wont be very ideal. In such cases averaging to curves would be better, in such cases the technique employed (+ve and -ve slope of line) to separate left and right lanes will not work i guess

### 3. Suggest possible improvements to your pipeline

One potential improvement
* to smoothen video, frame to frame line averaging could be done 

