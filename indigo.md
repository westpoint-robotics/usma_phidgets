# ---Work in progress---

### Installing from binary files:
- Install the Phidgets packages and one associated filter: `sudo apt-get install ros-indigo-phidgets-api ros-indigo-phidgets-drivers ros-indigo-phidgets-imu ros-indigo-imu-filter-madgwick`
- Switch to super user mode in order to update Udev rules: `sudo su`
- `echo 'SUBSYSTEMS=="usb", ACTION=="add", ATTRS{idVendor}=="06c2", ATTRS{idProduct}=="00[3-a][0-f]", MODE="666"' >> /etc/udev/rules.d/99-phidgets.rules`
- `udevadm control --reload-rules`
- Exit from su mode: `exit`
- Navigate to source of catkin workspace: `cd ~/catkin_ws/src` 
- Download our package: `git clone https://github.com/westpoint-robotics/usma_phidgets`
- Change directories to the root of your Catkin Workspace: `cd ~/catkin_ws`
- `catkin_make`
- `rospack profile`
- You can now launch the node: `roslaunch usma_phidgets imu.launch`

#### Troubleshooting
Some robot computers may not be able to locate the phidgets packages. To solve this add the ROS repositories using the following commands:
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
sudo apt-get update
```
