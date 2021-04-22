# autoware_calibration_camera_lidar
从autoware1.10中分离出来的lidar-camera联合标定工具，可支持在ubuntu18.04下使用并整合到autoware1.14中

安装及使用说明：
1、功能包中包含依赖功能包：nlopt.zip（使用别的nlopt版本可能导致无法运行标定工具），请解压后安装，并配置其环境：
    cd /etc/ld.so.conf.d
    sudo touch libnlopt.conf
    sudo gedit libnlopt.conf 
    之后，在libnlopt.conf文件中添加内容为：/usr/local/lib，然后使配置生效
    sudo ldconfig


2、下载源码到自己的工作空间中，此处使用colcon build进行编译，colcon build是catkin_make的升级版

3、然后添加运行库到环境中export LD_LIBRARY_PATH=~/<你的colcon build工作空间名字>/src/calibration_camera_lidar/lib


4、然后source ./install/setup.bash

5、新开一个终端执行roscore

6、当前终端执行rosrun calibration_camera_lidar calibration_toolkit。


可参考CSDN博客：https://blog.csdn.net/qq_43509129/article/details/109327157
