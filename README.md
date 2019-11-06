ros_canopen
===========

Canopen implementation for ROS.

[![Build Status](https://travis-ci.com/ros-industrial/ros_canopen.svg?branch=melodic-devel)](https://travis-ci.com/ros-industrial/ros_canopen)
[![License: LGPL v3](https://img.shields.io/badge/License-LGPL%20v3-blue.svg)](https://www.gnu.org/licenses/lgpl-3.0)
([![License: BSD 3-Clause](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause) for `can_msgs` and `socketcan_bridge`)

The current develop branch is `melodic-devel`, it targets ROS `melodic`. Needs C++14 compiler.
The released version gets synced over to the distro branch for each release.

## 事先安装muparser
安装方法见Install.txt文件

## socketcan_bridge_node节点运行注意
1 运行如下指令
```shell
sudo modprobe mttcan
sudo modprobe can
sudo modprobe can_raw
sudo ip link set can0 type can bitrate 500000 dbitrate 2000000 berr-reporting on fd on
sudo ip link set up can0
```
2 运行```ifconfig```(16.04) 或者 ```ip a```(18.04)查询CAN端口是否打开

3 运行```socketcan_bridge_node```
```shell
rosrun socketcan_bridge socketcan_bridge_node
```
