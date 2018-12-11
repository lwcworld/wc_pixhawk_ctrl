# installation
===========
- Gazebo & ROS environment
```
https://dev.px4.io/en/setup/dev_env_linux.html
```
- This package
```
git clone https://github.com/lwcworld/ETRI_FDI.git
```
- ROS and Gazebo env
```
cd <Path to this package>/install
./ubuntu_sim_ros_gazebo.sh
```

- PX4 Firmware
``` 
cd <PATH to install PX4>
git clone --branch v1.8.1 https://github.com/PX4/Firmware.git
cd Firmware 
git submodule update --init --recursive
make posix_sitl_default gazebo
```
- make soft link for "sitl_gazebo" directory to the catkin_ws/src 
``` 
ln -s <Path to PX4>/Tools/sitl_gazebo/ /home/<user>/catkin_ws/src/
cd catkin_ws
catkin build
```
