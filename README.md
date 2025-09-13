# OS and ROS version

OS: Ubuntu 22.04.5 LTS

ROS: ROS2 Humble

# Commands used in terminal
- The commands used were referred from the turtlebot3 website (https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/#pc-setup)

## Installing Gazebo, Cartographer, and Navigation 2
$ sudo apt install ros-humble-gazebo-*

$ sudo apt install ros-humble-cartographer

$ sudo apt install ros-humble-cartographer-ros

$ sudo apt install ros-humble-navigation2

$ sudo apt install ros-humble-nav2-bringup

## Installing Turtlebot3 packages
$ source /opt/ros/humble/setup.bash

$ mkdir -p ~/turtlebot3_ws/src

$ cd ~/turtlebot3_ws/src/

$ git clone -b humble https://github.com/ROBOTIS-GIT/DynamixelSDK.git

$ git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git

$ git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3.git

$ sudo apt install python3-colcon-common-extensions

$ cd ~/turtlebot3_ws

$ colcon build --symlink-install

$ echo 'source ~/turtlebot3_ws/install/setup.bash' >> ~/.bashrc

$ source ~/.bashrc

## Environment configuration
$ echo 'export ROS_DOMAIN_ID=30 #TURTLEBOT3' >> ~/.bashrc

$ echo 'source /usr/share/gazebo/setup.sh' >> ~/.bashrc

$ echo 'source /opt/ros/humble/setup.bash' >> ~/.bashrc

$ source ~/.bashrc

## Installing simulation packages
$ cd ~/turtlebot3_ws/src/

$ git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git

$ cd ~/turtlebot3_ws && colcon build --symlink-install

## Launching simulation with Gazebo and Rviz2
$ export TURTLEBOT3_MODEL=waffle

$ ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py

- with a different terminal:

$ ros2 launch turtlebot3_bringup rviz2.launch.py

## Launching the teleop navigation ( for robot simulation control)
$ ros2 run turtlebot3_teleop teleop_keyboard

- using WASDX keys to move the robot in the simulation
- W: forward, A: left, X: backward, D: right, S: stop

# Issues faced and how to fix them
1. Packages not installed
    - check for uninstalled package for ROS2 especially:
    - $ sudo apt install update
      
2. Rviz2 not showing the laser scan and sync with the Gazebo
    - running commands 1 by 1 accordingly with the turtlebot3 website guide

# Team member's name

Azmil bin Mohyidin
       
