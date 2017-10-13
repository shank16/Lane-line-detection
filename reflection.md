# **Finding Lane Lines on the Road** 
The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

Description
My pipeline consisted of 6 steps. 
1) I converted the images to grayscale
2) Applied Gaussian blurring to grayscale image
3)Applied Canny edged detection algorithm of OpenCV to blurred image
4) Applied region of Interest mask 
5) Applied Hough Transfomation to detect the lane_lines. 
6) Extrapolate the hough transformation Lines to get continuous lan_line detection

In order to draw a single line on the left and right lanes, I modified the draw_lines() function whic is according to following:

1) I made empty array for x and y points, slope, and intercept for both left and right side. 
2) Then I defined the slopes for righ and left side
3)I append the points, slopes and intercepts on empty arrays of respective sides.  
4) I averaged out the slopes and intercepts for line and use those to draw new smooth lines. 

Shortcomings:

My pipeline was working fine on test_images, however it has some problem in test_videos. Detected lines are  off from actual lanelines at certain time in videos.



Possible improvement:

1) change the canny parameters and hough transformation parameters to get more consistent detection of lane_lines

2) change draw_lines function to make it more robust and elegant by using python functions like polyfit or fitlines.  
