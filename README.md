# Udacity's Robotics Software Engineer nanodegree
#### Course website: [Robotics Software Engineer](www.udacity.com/course/robotics-software-engineer--nd209)

There are a total of 5 projects, starting off easy with ROS essentials and building a world in Gazebo, and 
ending with making a mobile robot perform a pickup-dropoff in an unknown map using the ROS navigation stack.

All media files can be found in the [media](https://github.com/imjaya/UDACITY_ROBOTICS_SWE/tree/master/media) folder.

## Projects
Project folders in this repository are complete on their own and require no additional downloads.
Contents of each project should be placed in the ```src``` folder of the catkin workspace. To avoid any possible conflicts,
it's advised to have a separate workspace for every project.

_Requirements_: **Ubuntu 16.04** and **ROS Kinetic**

_Dependencies_: listed in every project's README (will be updated, check back soon!)

Before getting started, open the terminal and execute this line:
```
sudo apt-get update && sudo apt-get upgrade -y
```

### Project 1: Build My World
An introduction to Gazebo: creating models and buildings and populating a world with them. ```world``` files created in this project were used in the subsequent projects.

### Project 2: Go Chase It!
A very basic visual servoing task in which a differential drive mobile robot detects and pursues a ball.

![](media/Project2%20media/ball_chaser.gif)

### Project 3: Where Am I
Given a map generated by ```pgm_map_creator```, Adaptive Monte Carlo Localization (also called particle filter localization) is used to localize the robot. As can be seen from the converging yellow markers, only the first few sensor updates are sufficient for the robot to be confident enough of its location relative to the map. 

ROS package used: ```amcl```

Initial guesses             |  Estimates after first few sensor updates
:-------------------------:|:-------------------------:
![](media/Project3%20media/starting_point.png)  |  ![](media/Project3%20media/final_localization.png)

Example 1             |  Example 2
:-------------------------:|:-------------------------:
![](media/Project3%20media/localization1.gif)  |  ![](media/Project3%20media/localization2.gif)

### Project 4: Map My World
This project assumes known robot pose to map an environment. The robot uses camera data to recognize previously visited regions in the map using a graph-based SLAM approach known as Real-Time Appearance Based (RTAB) mapping (under the hood, bag-of-words is used for detecting loop closures). More information on this can be found [here](http://introlab.github.io/rtabmap/). 

ROS package used: ```rtabmap_ros```
Actual world in Gazebo             |  Map created by RTAB mapping
:-------------------------:|:-------------------------:
![](media/Project4%20media/Lworld.png)  |  ![](media/Project4%20media/Lshaped_world.png)
![](media/Project4%20media/small_warehouse_gazebo.png)  |  ![](media/Project4%20media/small_warehouse_world.png)

### Project 5: Home Service Robot
This is where all the previous projects come together. ```gmapping``` is used to create a map in which the turtlebot then traverses from the starting point to the drop-off point via the pick-up waypoint. The package is represented by a 
![#1589F0](https://via.placeholder.com/15/1589F0/000000?text=+) marker.

![](media/Project5%20media/homeServiceRobot.gif)
