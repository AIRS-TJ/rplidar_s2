# rplidar_s2

## 1. Installation

### 1.1. Install enviroment

* Ubuntu 18.04.6 LTS + ROS melodic

ros melodic install refer:http://wiki.ros.org/melodic/Installation/Ubuntu

### 1.2. Install cartographer

参考:https://google-cartographer-ros.readthedocs.io/en/latest/compilation.html

注意：需要翻墙

	$ sudo apt-get update
	$ sudo apt-get install -y python-wstool python-rosdep ninja-build stow

	$ mkdir catkin_ws
	$ cd catkin_ws
	$ wstool init src
	$ wstool merge -t src https://raw.githubusercontent.com/cartographer-project/cartographer_ros/master/cartographer_ros.rosinstall
	$ wstool update -t src
	$ sudo rosdep init
	$ rosdep update
	$ rosdep install --from-paths src --ignore-src --rosdistro=melodic -y
	$ src/cartographer/scripts/install_abseil.sh
	$ sudo apt-get remove ros-melodic-abseil-cpp
	
### 1.3. Install source code

	$ cd ~/catkin_ws/src 
	$ git clone https://github.com/AIRS-TJ/rplidar_s2.git
	
### 1.4. 编译

	$ cd ~/catkin_ws/

	$ catkin_make_isolated --install --use-ninja 
	
### 1.5. souce环境变量：

	$ gedit ~/.bashrc 
	
	在末尾添加:
	
	source ~/catkin_ws/install_isolated/setup.bash

## 2. rplidar_s2激光使用

### ROS驱动

	$ sudo chmod 777 /dev/ttyUSB0 

	$ roslaunch rplidar_ros view_rplidar_s2.launch 
	
### 只用rplidar_s2激光没有imu运行cartographer建图

	$ roslaunch cartographer_rplidar_s2 demo_rplidar_s2_2d.launch
