# Packages for Dynamixel Motors

Author: [Aravind Narayanan](https://github.com/aravind-3105) 

For any doubts, feel free to contact me on MS Teams: aravind.narayanan@students.iiit.ac.in

# Downloading Dynamixel packages:

```bash
$cd ~/catkin_ws/src
$git clone https://github.com/ROBOTIS-GIT/dynamixel-workbench.git
$cd dynamixel-workbench/
$git checkout -b melodic-devel
$cd dynamixel_workbench_toolbox/examples
$mkdir -p build && cd build
$cmake ..
$make

$cd ~/catkin_ws/src
$git clone https://github.com/ROBOTIS-GIT/dynamixel-workbench-msgs.git
$cd dynamixel-workbench-msgs/
$git checkout -b melodic-devel

$cd ~/catkin_ws/src
$git clone https://github.com/ROBOTIS-GIT/DynamixelSDK.git
$cd dynamixel-workbench-msgs/
$git checkout -b melodic-devel
```

P.S note that ROS melodic is the ROS version used for ubuntu 18.04. If you have ubuntu 20.04 use ROS Noetic.

# Device Setup

Information about U2D2 board: [https://emanual.robotis.com/docs/en/parts/interface/u2d2/](https://emanual.robotis.com/docs/en/parts/interface/u2d2/)

Download relevant files

```bash
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/dynamixel-workbench/master/99-dynamixel-workbench-cdc.rules
$ sudo cp ./99-dynamixel-workbench-cdc.rules /etc/udev/rules.d/
$ sudo udevadm control --reload-rules
$ sudo udevadm trigger
```

After connecting the motor to PC through the U2D2, to check which usb port it is connected to:

`$ ls /dev/tty*`

Ideally you should find one which starts with /dev/ttyUSB.

# Using the dynamixel motors with ROS

In the first terminal run:

$`roscore`

In another terminal run:

$`rosrun dynamixel_workbench_controllers find_dynamixel /dev/ttyUSB0`

Expected output:

![Untitled](Packages%20for%20Dynamixel%20Motors%206745707153ef4473ba8003856cdf3f0b/Untitled.png)

Then run:

`roslaunch dynamixel_workbench_controllers dynamixel_controllers.launch`

Expected Output:

![Untitled](Packages%20for%20Dynamixel%20Motors%206745707153ef4473ba8003856cdf3f0b/Untitled%201.png)

Then type: `rqt`  in a separate terminal, the following GUI would open:

![Untitled](Packages%20for%20Dynamixel%20Motors%206745707153ef4473ba8003856cdf3f0b/Untitled%202.png)

After adjustment of the mentioned values, you should be able to see the motor rotate.

If the above steps work properly, then it is verification that the packages and connections are done properly.

![Untitled](Packages%20for%20Dynamixel%20Motors%206745707153ef4473ba8003856cdf3f0b/Untitled%203.png)

To view information published on the above mentioned topics:

`rostopic echo {insert_topic_name_list}`

# To play a series of motions:

Will be updated after explanation in the tutorial.

# References:

[https://emanual.robotis.com/docs/en/software/dynamixel/dynamixel_workbench/](https://emanual.robotis.com/docs/en/software/dynamixel/dynamixel_workbench/)
