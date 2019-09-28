# CarND-Path-Planning-Project
Udacity Self-Driving Car Engineer Nanodegree Program. 

[image1]: ./result/one_loop.png "one loop"
[image2]: ./result/lane_change.png "lane change"

![alt text][image1]

### Overview
This project is to implement a path planning algorithm to safely navigate around a virtual highway with other traffic. 
The car's localization and sensor fusion data are provided by a simulator. There is also provided a sparse map list of waypoints around the highway. 
The car should avoid hitting other cars at all cost as well as driving inside of the marked road lanes at all times, unless going from one lane to another. 

### Content
* README.md: the report
* src: source code, main.cpp contains the path planning implementation, spline.h is the picewise polynominal fitting helper function.
* ProjectDescription: the original readme.md for project details

### Compilation
1. Make a build directory: `mkdir build && cd build`
2. Compile: `cmake .. && make`
3. Run it: `./path_planning`.

### Valid Trajectories
The car is able to drive at least 4.32 miles without incident. 
The car doesn't drive faster than the speed limit. Also the car isn't driving much slower than speed limit unless obstructed by traffic.
The car does not exceed a total acceleration of 10 m/s^2 and a jerk of 10 m/s^3.
It has no collisions. 
It stays in its lane and is able to change lanes as the screenshot below.

![alt text][image2]

### Reflection
There are mainly two parts in how to generate path: behavior prediction and trajectory generation.

In ```src/main.cpp``` line 179 - 286 are the code for creating trajectory. This gets the car to move. 
The previous path is used to make position transition more smoothy (line 203 - 215).

Behavior prediction is from line 103 - 177. This checks the cars around our car, and make decisions on lane change and/or speed change.


