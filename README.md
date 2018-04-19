# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)


Overview
---

This is the firts Project due for the Udacity Self-Driving Car Nanodegree, after the Computer Vision Fundamentals Module.

For it, the goal is to identify the Left and Right lanes, in a set of images first and a video feed later, taken from a camer mounted in a fixed position in front of a moving car. The lanes are then drawn on the original image/video stream, as continuous lines.

Specifically, three steps can be identified:

1. The building of a pipeline for line identification, that can take road images and video as input and return them with annotations;
2. The pipeline implements generic helper functions that were provided upfront;
3. Thos functions have also been extended to build continuous lines to identify lanes;

To complete the project, two files are submitted and part of this Git repo: a file containing project [code](https://github.com/udacity/CarND-LaneLines-P1/blob/master/P1.ipynb) in the forme of a Jupyther Python notebook and an annotated [writeup](https://github.com/udacity/CarND-LaneLines-P1/blob/master/writeup_template.md) describing the fundamental aspects and limitations of the solution implemented.

