# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)
<iframe src="test_videos_output/solidYellowLeft.mp4" width="960" height="540" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project you will detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.  


The Project
---
Reflection
### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps:
```
  Convert the image to grayscale.
  
  Gausian smoothing and apply Canny edge detection.
  
  Mask other areas of the image.
  
  Apply Hough Transform to detect lane lines.
  
  Draw the lane lines on the original image.
 ```
In order to draw lines on the left and right lanes, I converted the lines from Hoff to a slope greater than 0.4 and less than 0.8. Divide these lines into positive and negative (left and right), and find the average slope, and the average BIAS, find <code>y=mx+b</code>, find the points at the bottom and bottom of MASK, and draw them.

### 2. Identify potential shortcomings with your current pipeline

<iframe src="test_videos_output/challenge.mp4" width="960" height="540" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

At present, I use the weight method to balance the offset and noise, but there will still be some slight errors. I think I can enhance the image pre-processing.
