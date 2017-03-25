# usma_phidgets
Instructions to use the Phidgets 1044 IMU

### Installing from binary files:
- Install the Phidgets packages and one associated filter: `sudo apt-get install ros-kinetic-phidgets-api ros-kinetic-phidgets-drivers ros-kinetic-phidgets-imu ros-kinetic-imu-filter-madgwick`
- Switch to super user mode in order to update Udev rules: `sudo su`
- `echo 'SUBSYSTEMS=="usb", ACTION=="add", ATTRS{idVendor}=="06c2", ATTRS{idProduct}=="00[3-a][0-f]", MODE="666"' >> /etc/udev/rules.d/99-phidgets.rules`
- `udevadm control --reload-rules`
- Exit from su mode: `exit`
- Navigate to root of catkin workspace: `cd ~/catkin_ws/src` 
- Download our package: `git clone https://github.com/westpoint-robotics/usma_phidgets`
- Change directories to the root of your Catkin Workspace by typing  `cd ~/catkin_ws`
- `catkin_make`
- `rospack profile`
- You can now launch the node: `roslaunch usma_phidgets imu.launch`

#### For documentation regarding nodes and topics, view the package summary on [ROS Wiki](http://ros.org/wiki/phidgets_drivers).
