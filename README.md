# Lane Line Detection Project1

Lane Line Detection Algorithm Project1.

When we drive, we use our eyes to decide where to go. The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle. Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project I will detect lane lines in images using Python and OpenCV. OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

### Reflection

### 1. Lane Line Detection Project PipeLine

My pipeline consisted of the following steps below:
1. Take a single 3-channel RGB image and then convert the image to grayscale i.e. one color channel image.
2. Reduce the noise using GaussianBlur function.
3. Apply Canny Edge Detection on the smoothed gray image to detect the edges on the image.(I use (55,110) as low threshold and high threshold respectively in canny function).
4. Trace Region Of Interest and discard all other lines identified by our previous step that are outside this region.
5. Perform Hough Transformation to find lanes within our Region Of Interest and trace them in red color.
6. Modifying the draw_lines() function, I separate the left and right lanes using the slope of the line.
7. Then I interpolate line gradients to create two smooth lane lines.


### 2. Potential shortcomings with the current pipeline

I observed some problems with the current pipeline:
1. Where there is a curve on the road, the straight lines don't work properly.
2. I think in the Lane Line detection on the videos, after each frame the slope of the lane line changes. But I am not able to update the slope for each and every frame.
3. Hough Transform is a bit trickier to get its correct parameters. I tried my best but not sure about its best parameter values.
4. Also both the Lane Lines got intersect each other at some point.

### 3. Possible improvements in the pipeline

A possible improvement could be to get each frames of the video and to be able to update the slope in each frame so that lines would not go off the lanes.
Another potential improvement could be to make sure the lane lines do not intersect each other.
I would also love to use deep learning techniques to detect lane lines and compare both the results.



This is an exciting and challenging first project that got me to understand the concepts of image processing, computer vision and linear algebra also and apply all these things to detect the lane lines on the road. Looking forward to learn and do even more challenging projects.
