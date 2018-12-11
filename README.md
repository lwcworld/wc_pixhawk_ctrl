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
- PX4 Firmware upload to Pixhawk board (pixhawk4 board)
``` 
cd <PATH to Firmware>
make px4_fmu-v5_default 
make px4_fmu-v4_default upload
```
- PX4 SITL
make soft link for "sitl_gazebo" directory to the catkin_ws/src 
``` 
ln -s <Path to Firmware>/Tools/sitl_gazebo/ /home/<user>/catkin_ws/src/
cd catkin_ws
catkin build
```
