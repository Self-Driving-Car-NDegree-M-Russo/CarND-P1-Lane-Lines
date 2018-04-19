# **Finding Lane Lines on the Road** 

## Project Writeup 

[//]: # (Image References)

[image1]: ./examples/initial_image.jpg "StartingImage"
[image2]: ./examples/final_img.jpg "FinalImage"

---

### Pipeline Description

The implemented pipeline consisted of 6 steps. 

Starting from an image :

![alt_text][image1]

1. Convert it in gray scale; 
2. Apply Gaussian Blur;
3. Apply Canny Edge detection;
4. On top of the identified edges apply a mask selecting a portion of the image area only;
5. Apply the Hough Transformation to identify the line segments corrensponding to the lanes;
6. Extreapolate the segments to build contiuous lines and draw them on top of the initial image.

The final image will be:

![alt text][image2]

---

### Notes

A couple more steps are actually available (even if commented out) in the code. They can be helpful for troubleshooting, (for example, we can plot lines on top of the Canny edges, to verify consistency of the process) but do not affect the actual final image

The extrapolation from segments to continuous lines follows this sequence:

- Each line segment is expressed in the form y = (m * x) + n;
- Left and right lanes are identified by the sign of the angular coefficient (<0 for left, >0 for right);
- An average angular coefficient/parameter couple is calculated from the segments belonging to each lane;
- Two continuous lines are then drawn based on this average values.

---

### Shortcoming and Improvements

The most significant shortcoming of this solution is most likely its reliance on a set of information that are assumed to stay constant but can actually change depending on the environment:

* For example, the mask applied in step 4. of the pipeline (a triangular one that extends from the bottom of the image to a point in its middle) works for this camera mounting, but would not work for different positions, that could bring objects like the car hood in the field of view. More sophisticated solution could provide the possibility to select different masks for different configurations.

* Another possible improvement could be in the area of the parameters used by the various functions, from the thresholds in the Canny edge detection to the ones used by the Hough transformation. These values here stay constant through the video feed, which is fine given that short duration, but on a real-life scenario the car could run into different light or weather conditions, where a different "tuning" might be advisable. In this scenario, and adptive solution capable of monitoring different sensors might even change these values in real time.

* Finally, the extrapolation of lines makes it so tha thay are of a given pre-defined size (they stop at a given y-coordinate in the image). Here again, more sophisticated solution could adapt this based on, for example, the car's speed.

