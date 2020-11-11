# **Finding Lane Lines on the Road** 
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/solidWhiteCurve.jpg

---

### Reflection
My pipeline consisted of the following 6 steps. 
1. I converted the images to grayscale.
2. I have then applied Gaussian Blur on the image to smoothen the image.
3. Used Canny edge detection algorithm to detect edges in the image using OpenCv.
4. Applied masking to get the region of interest from the image, this region of interest mainly has the lane lines which we want to identify.
5. Used Hough Transform to extract the lane lines from the image, and also used the draw_lines() function to calculate the average slope of both the left and right lanes that were identified using Hough Transform.Used OpenCv to draw a line to mark the full extent of the lane as in the example video (P1_example.mp4)
6. Used weighted_img() function to super impose the lines generated in the above step on the initial image which was passed to the process image pipeline.

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the road has a blind turn resulting in steep curves in the lanes. 

Another shortcoming could be for the crossroads where multiple potential candidates for the lane lines could be detected as multiple lines can be present in the region of interest.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to add a function in the beginning of the pipeline that could self calibrate threshold values used in the pipeline so that the pipeline can handle images having different lighting conditions.

Another potential improvement could be to look for other computer vision techniques to address the given problem statement.
