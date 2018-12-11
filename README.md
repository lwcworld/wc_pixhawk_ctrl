# installation
- Pixhawk/NuttX toolchain for hardware firmware build
```
https://dev.px4.io/en/setup/dev_env_linux.html
```
- Gazebo & ROS environment for SITL
```
https://dev.px4.io/en/setup/dev_env_linux.html
```
- This package
```
https://github.com/lwcworld/wc_pixhawk_ctrl.git
```
- build proper firmware & upload to Pixhawk board (pixhawk4 board)
``` 
cd <PATH to Firmware>
make px4_fmu-v5_default 
make px4_fmu-v4_default upload
```
- PX4 SITL
1. build SITL
'''
cd <PATH to Firmware>
make posix_sitl_default gazebo
'''
2. make soft link for "sitl_gazebo" directory to the catkin_ws/src 
``` 
ln -s <Path to Firmware>/Tools/sitl_gazebo/ /home/<user>/catkin_ws/src/
cd catkin_ws
catkin build
```

# run SITL
1. source dependent packages
'''
cd <PATH to Firmware>
'''
'''
source ~/catkin_ws/devel/setup.bash
'''
'''
source Tools/setup_gazebo.bash $(pwd) $(pwd)/build_posix_sitl_default
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)/Tools/sitl_gazebo
'''

2. launch SITL
'''
roslaunch px4 mavros_posix_sitl.launch 
'''

3. run code
