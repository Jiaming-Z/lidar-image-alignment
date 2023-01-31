# lidar-image-alignment
2D-2D alignment homography rough draft version, 01/30/23
Description:
I used homography estimation to formulate a H matrix using 4 manually selected data points on each of the two images that correspond to each other, 
with these data points inputed, this program is able to give a H matrix that could project a point of of the lidar image to the camera image.

How to use:
If you want to re-estimate the H matrix, follow steps 1-2, otherwise (using H matrix estimated by 4 pre-determined points) skip directly to step 3
1, use Pix Spy https://pixspy.com/ to find 4 pairs of corresponding pixel coordinates on the lidar and camera images
2, input these data points as x1-4, y1-4 (lidar image horizontal and vertical points) and u1-4, v1-4 (camera image horizontal and vertical points)
3, run the next code block to get the H matrix
4, now we have the homography matrix H, input any pixel point within bound of the lidar image as X, Y, and run the final code box
5, will get the homogeneous and cartesian coordiante estimate of the point chosen on the camera image
