# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<a href="http://www.youtube.com/watch?feature=player_embedded&v=VehTDTVKKSM" target="_blank"><img src="http://img.youtube.com/vi/VehTDTVKKSM/0.jpg" 
alt="This My test video" width="960" height="540" border="10" /></a>
### This My test video
Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project you will detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.  

[//]: # (Image References)

[image1]: ./test_images_output/gray_image_solidYellowLeft.jpg "gray_image_solidYellowLeft"
[image2]: ./test_images_output/blur_gray_image_solidYellowLeft.jpg "blur_gray_image_solidYellowLeft"
[image3]: ./test_images_output/edge_image_solidYellowLeft.jpg "edge_image_solidYellowLeft"
[image4]: ./test_images_output/masked_edge_image_solidYellowLeft.jpg "masked_edge_image_solidYellowLeft"
[image5]: ./test_images_output/hough_image_solidYellowLeft.jpg "hough_image_solidYellowLeft"
[image6]: ./test_images_output/solidYellowLeft.jpg "solidYellowLeft"

#The Project
---
## 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of some steps.

###  converted the images to grayscale
  ![alt text][image1]
###  Gausian smoothing image
  ![alt text][image2]
###  apply Canny edge detection.
  ![alt text][image3]
###  Mask other areas of the image.
  ![alt text][image4]
###  Apply Hough Transform to detect lane lines.
  ![alt text][image5]
###  Draw the lane lines on the original image.
  ![alt text][image6]
 ```
In order to draw lines on the left and right lanes, I converted the lines from Hoff to a slope greater than 0.4 and less than 0.8. Divide these lines into positive and negative (left and right), and find the average slope, and the average BIAS, find <code>y=mx+b</code>, find the points at the bottom and bottom of MASK, and draw them.

### 2. Identify potential shortcomings with your current pipeline

<a href="http://www.youtube.com/watch?feature=player_embedded&v=u2hl9mk0WSQ" target="_blank"><img src="http://img.youtube.com/vi/u2hl9mk0WSQ/0.jpg" 
alt="This My Challenge video" width="960" height="540" border="10" /></a>
### This My Challenge video

At present, I use the weight method to balance the offset and noise, but there will still be some slight errors. I think I can enhance the image pre-processing.
