# Setup
Prerequisites:
 - Ubuntu 20.04
 - ROS Noetic (only tested on this version)
 - unitree_ros
 - unitree_ros_to_real
 - unitree_legged_sdk
 - z1_sdk
 - z1_controller

Setup catkin workspace
```
$ source /opt/ros/noetic/setup.bash
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/
$ catkin_make
```

Install unitree_ros, unitree_ros_to_real, unitree_legged_sdk, z1_sdk, and z1_controller
```
$ cd src
$ git clone --recurse-submodules https://github.com/unitreerobotics/unitree_ros.git
$ cd ..
$ catkin_make
$ source devel/setup.bash
$ git clone https://github.com/paulblum/z1_controller.git
```

Make the Z1 controller:

2. Open another terminal
```
$ cd ~/unitree_ws                                                        
$ source devel/setup.bash
$ cd ~/unitree_ws/z1_controller
$ mkdir build
$ cd build
$ cmake ..
$ make
```


# Launching and Running AliengoZ1
Setting up the environment:

1. Open a terminal
```
$ cd ~/unitree_ws                                                        
$ source devel/setup.bash
```                  

___
Run AliengoZ1

Open a new terminal
```
$ cd ~/unitree_ws                                                        
$ source devel/setup.bash
$ roslaunch aliengoZ1_description aliengoZ1_gazebo.launch
```
- This will open up gazebo with the robot.
___

Run the Z1 controller:

Open a new terminal
```
$ cd ~/unitree_ws/z1_controller/build                                                        
$ source ../../devel/setup.bash
$ ./sim_ctrl k
```
press 2 and 3 on your keyboard to set up the robot to control 

![image](https://github.com/ansonchen04/z1_controller/assets/148047458/5b188fe4-1c8e-4394-b01e-1cee8f87bb68)

reference https://dev-z1.unitree.com/use/keyboard.html

 - 2: Caliberates the joints to 'zero'

 - 3: Switches coordinate system to Cartesian coordinates

___
Make the robot stand:

3. Open another terminal
```
$ cd ~/unitree_ws
$ source devel/setup.bash
$ rosrun unitree_controller unitree_servo
```
___
RQT (Optional):

4. Open another terminal
```
$ cd ~/unitree_ws
$ source devel/setup.bash
$ rqt_graph
```
___
Documentation:

[unitree-z1-docs-en](http://dev-z1.unitree.com)

[unitree-z1-docs-cn](http://dev-z1.cn.unitree.com)


