# rplidar_s2

## 安装

首次要安装好cartographer_ros

然后在src下

	$ git clone https://github.com/AIRS-TJ/rplidar_s2.git
	
再编译

## rplidar_s2激光使用

### ROS驱动

	$ sudo chmod 777 /dev/ttyUSB0 

	$ roslaunch rplidar_ros view_rplidar_s2.launch 
	
### 只用rplidar_s2激光没有imu运行cartographer建图

	$ roslaunch cartographer_rplidar_s2 demo_rplidar_s2_2d.launch
