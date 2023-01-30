# CameraCalibration

## Overview
This code uses the OpenCV library to perform camera calibration on a set of images, and then uses the resulting camera parameters to calculate the reprojection error of each image. The code also visualizes the points distribution and the reprojection error distribution.

## Dependencies
This code requires the following libraries:

-OpenCV


-NumPy


-Matplotlib


-os


-pickle

## Usage
Obtain a set of images with a known chessboard pattern.
Run the code, providing the path to the images and the chessboard pattern dimensions as inputs.
The code will output the camera parameters and a visualization of the points distribution and the reprojection error distribution.

## Code walkthrough
First, the necessary libraries are imported.

Then, the camera matrix, distortion coefficients, and image size of the camera are defined. The distortion coefficients are set to simulate a camera with and without a dome distortion.

Next, 3D points in the world space are defined and their corresponding 2D projections are calculated using the cv2.projectPoints() function.

The reprojection errors are then calculated by comparing the original 3D points with their reprojected 2D points, and are stored in two separate lists: one for the camera with a dome distortion and one for the camera without a dome distortion.

Finally, the reprojection errors are plotted on scatter plots, with the x and y coordinates of the 2D points on the x and y axes, respectively, and the color of the points representing the error values. The plot for the camera with a dome distortion is shown on the left, and the plot for the camera without a dome distortion is on the right. The plot is saved as "reprojection_error_distribution.pdf" in the output path.

The code shows that the reprojection errors are higher for the camera with a dome distortion, indicating that the dome distortion affects the accuracy of the camera model.

![alt text](https://github.com/bridges77/CameraCalibration/blob/main/reprojection_error_distribution-1.png)

