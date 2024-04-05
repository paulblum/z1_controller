# Launching and Running AliengoZ1
Setting up the environment:

1. Open a new terminal
~~~
roscore
~~~
___
2. Open another terminal
~~~
cd ~/unitree_ws                                                        
source devel/setup.bash
catkin_make
source devel/setup.bash
~~~
___                     
Run the AliengoZ1 in Gazebo:
~~~
roslaunch aliengoZ1_description aliengoZ1_gazebo.launch
~~~
- This will open up gazebo with the robot.
___
Compile and run Z1 controller

3. Open another terminal
~~~
cd ~/unitree_ws                                                        
source devel/setup.bash
cd ~/unitree_ws/z1_controller
mkdir build
cd build
cmake ..
make
./sim_ctrl k
~~~
press 2 and 3 on your keyboard to set up the robot then to control 

reference https://dev-z1.unitree.com/use/keyboard.html

 - 2: Caliberates the joints to 'zero'

 - 3: Switches coordinate system to Cartesian coordinates
___
Make the robot stand:

4. Open another terminal
~~~
cd ~/unitree_ws
source devel/setup.bash
rosrun unitree_controller unitree_servo
~~~
___
RQT (Optional):

5. Open another terminal
~~~
cd ~/unitree_ws
source devel/setup.bash
rqt_graph
~~~
___
Documentation:

[unitree-z1-docs-en](http://dev-z1.unitree.com)

[unitree-z1-docs-cn](http://dev-z1.cn.unitree.com)


