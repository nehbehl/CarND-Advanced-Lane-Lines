## Advanced Lane Finding
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)
![Lanes Image](./examples/curvature_img.jpg)

The Project
---

The goals / steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.


Let's talk about each step one by one and how I implemented it!

Note: All output images can be found at './output_images'

# First step - Camera Calibration

In this step, I fetch object points using real pictures of chessboard and derive chessboard corners from same. Then I use the derived object points and map them onto 2-D image points. Finally, I use cv2.calibrateCamera() method to retrieve the camera matrix and distortion coefficients. This code resides at './camera_cal/camera_calibration.ipynb' and values for mtx and dist have been saved in a pickle file to be retrieved in the code below.

# Second step - Apply distortion correction to raw images
In this step, the camera matrix and distortion coefficients are used to undistort the raw images.


# Third step - Create thresholded binary image

In this step, gradient values and color spaces are used to fetch a thresholded binary image which uses HLS and HSV channel filtration and a combined threshold is applied.


# Fourth step - Apply a perspective transform

In this step, perspective transformation is applied to get the warped image which is a bird's eye view of the region of interest.


# Fifth step - Detect lane pixels and fit to find the lane boundary

In this step, histogram values are used to get the areas with high pixel values which are further used to detect the lane pixels and boundaries of left and right side of the lane lines.


# Sixth step - Determine the curvature of the lane and vehicle position with respect to center

In this step, the identified lane pixel values help to determine the radius of curvature and position of the vehicle from the center.


# Seventh step - Inverse Transform

In this step, the identifed lane boundaries are mapped back onto the original image by using inversed perspective transform.


# Eighth step - Output visual display

In this step, the radius of curvature and offset from center values are visually displayed on the image.
