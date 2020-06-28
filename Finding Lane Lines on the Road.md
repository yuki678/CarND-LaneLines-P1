# Finding Lane Lines on the Road

[//]: # (Image References)
[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./examples/canny.png "Canny"
[image3]: ./examples/region_interest.png "Region"
[image4]: ./examples/detected_lines.png "Lines"
[image5]: ./examples/combined.png "Combined"

---

## Project Goal
Make a pipeline that finds lane lines on the road

## Reflection

### 1. Pipeline

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied Gaussian Blur to remove noises. 

![alt text][image1]

After detecting the edges by Canny transform, I masked the image to leave only a region of interest. 

![alt text][image2]
![alt text][image3]

Then, I applied Hough Transform to find lines and finally combined the lines and the original image.

![alt text][image4]
![alt text][image5]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function as follows:

1. For each line detected,
   1. Calculate a slope of the line
   2. If the slope is within thresholds, take the slope and both end points for left line or right line depending on the sign 
2. Calculate a single line for each or the left and right by
   1. Slope - take the median of all the slopes
   2. Intercept - draw a line which passes the median of all the end points
   3. End of lines - take the maximum and minimum values for x

### 2. Potential shortcomings with this pipeline

One potential shortcoming would be what would happen when the lane is not straight. This detection does not work at corners of a road.
Another shortcoming could be it cannot draw a complete line when the lane line is dotted or blur.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use polynomial function to calculate lines. 
Another potential improvement could be to use moving average of previous frames rather than the fixed threshold to remove noises and calculate the end points of lines.
