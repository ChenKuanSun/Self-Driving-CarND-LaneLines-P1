# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/gray_image_solidYellowLeft.jpg "gray_image_solidYellowLeft"
[image2]: ./test_images_output/blur_gray_image_solidYellowLeft.jpg "blur_gray_image_solidYellowLeft"
[image3]: ./test_images_output/edge_image_solidYellowLeft.jpg "edge_image_solidYellowLeft"
[image4]: ./test_images_output/masked_edge_image_solidYellowLeft.jpg "masked_edge_image_solidYellowLeft"
[image5]: ./test_images_output/hough_image_solidYellowLeft.jpg "hough_image_solidYellowLeft"
[image6]: ./test_images_output/solidYellowLeft.jpg "solidYellowLeft"


---

# Reflection

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

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by 
```
In order to draw lines on the left and right lanes, 
I converted the lines from Hoff to a slope greater than 0.4 and less than 0.8. 
Divide these lines into positive and negative (left and right), and 
find the average slope, and the average BIAS, find <code>y=mx+b</code>, 
find the points at the bottom and bottom of MASK, and draw them.
```

### 2. Identify potential shortcomings with your current pipeline

```
At present, I use the weight method to balance the offset and noise, but there will still be some slight errors.
```

### 3. Suggest possible improvements to your pipeline

```
 I think I can enhance the image pre-processing.
```
