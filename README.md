# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---
This is the first project of Self-driving Car Nanodegree at Udacity.

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project, detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.  

Installation
---
No specific installation required apart from python 3.x and its libraries. Required libraries specific to this project are:
 - pip install opencv-python
 - pip install moviepy

Project Description
---
The process to draw a lane line on to the images and videos are as follows:

#### Image
1. Load an image
2. Make it as gray scale
3. Apply Gaussian Blur to remove noises
4. Apply Canny transformation to detect edges
5. Mask the image to leave only a region of interest
6. Apply Hough Transform to find lines
7. Combine the line and the original image

#### Video
Almost the same as image processing, just load/write videos instead of an image.
1. Load clips of the video using VideoFileClip
2. Pass the same pipeline (step 2 to 7) to VideoFileClip.f1_image()
3. Save the output to a video file using VideoFileClip.write_videofile()

Please read Finding Lane Lines on the Road.md for the project findings.

Files
---
 * P1.ipynb - this contains all the code in this project
 * Finding Lane Lines on the Road.md - Project write-up.
 * set_git.sh - a shell script to set github repository configurations
 * test_images/ - contains all test image files
 * test_videos/ - contains all test video files
 * examples/ - some example output files
 * test_video-output/ - output from P1.ipynb is saved here
 * LICENSE - contains license info

License
---
Entire contents of this project attribute to Udacity. Please refer to LICENSE file.