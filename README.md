lidar-image-alignment

(UPDATE 03/09/23): Uploaded updatd file with newly improved method that only require 6 points, also eliminate R,t ambiguity and add calculation for reprojection error

(UPDATE 03/02/23): Uploaded the successfully functional 3D->2D alignment code using epipolar constraint and Essential matrix, could find R and t using minimum of 9 points, previous code using homography method proven WRONG since it doesn't provide proper R and t values


Homography Stuff below, unusable in lidar-camera calibration

(UPDATE 02/12/23): Uploaded 3D lidar to image projection code, the 6 pair-input svd method works, the more "efficient" 3 pair-input methods doesn't currently work.

(UPDATE 02/04/23): There are now multiple methods to generate the H matrix, you can use whichever one you like, but I would recommand using the one with the minimum condition number to get the most precise projection. You can also try finding the H matrix yourself using another method and use the given code of finding condition number to determine the goodness of fit

2D-2D alignment homography rough draft version, 01/30/23

Description:
I used homography estimation to formulate a H matrix using 4 manually selected data points on each of the two images that correspond to each other, 
with these data points inputed, this program is able to give a H matrix that could project a point of of the lidar image to the camera image.

How to use:

If you want to re-estimate the H matrix, follow steps 1-2, otherwise (using H matrix estimated by 4 pre-determined points) skip directly to step 3

1, use Pix Spy https://pixspy.com/ to find 4 pairs of corresponding pixel coordinates on the lidar and camera images

2, input these data points as x1-4, y1-4 (lidar image horizontal and vertical points) and u1-4, v1-4 (camera image horizontal and vertical points)

3, choose your preferred method and run the corresponding code block to get the H matrix

4, now we have the homography matrix H, input any pixel point within bound of the lidar image as X, Y, and run the final code box

5, will get the homogeneous and cartesian coordiante estimate of the point chosen on the camera image
