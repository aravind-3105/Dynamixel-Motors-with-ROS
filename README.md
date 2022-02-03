# Installation of Robotic Operating System

Author: [Aravind Narayanan](https://github.com/aravind-3105) 

For any doubts, feel free to contact me on MS Teams: aravind.narayanan@students.iiit.ac.in

## 1. Setup sources.list:

```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

## 2. Setup your keys

```bash
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

## 3. Installation

```bash
sudo apt update
```

**Desktop-Full Install**: ROS, [rqt](http://wiki.ros.org/rqt), [rviz](http://wiki.ros.org/rviz), robot-generic libraries, 2D/3D simulators and 2D/3D perception

- `sudo apt install ros-melodic-desktop-full`

**To install particular Individual Packages:** Replace {package-name} with dashes of the package name:

- `sudo apt install ros-melodic-{PACKAGE-NAME}`

# Post installation setup

## Environment Setup:

There are usually two standard methods of environment:

1. `echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc`
`source ~/.bashrc`

**(or)**

1. `source /opt/ros/melodic/setup.bash`

## **Dependencies for building packages**

1. `sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential`
2. Initialize rosdep to easily install system dependencies for source you want to compile and is required to run some core components in ROS:
    
    `sudo apt install python-rosdep`
    
    To initialise:
    
    `sudo rosdep init`
    
    `rosdep update`
    

# Creating a ROS Workspace

To run and save ros files, we create a workspace and save the packages there.

`mkdir -p ~/catkin_ws/src`

`cd ~/catkin_ws/`

`catkin_make`

To run ROS file, we need to run the following in every new terminal.

`source devel/setup.bash`

We see there are three main folders: build, devel and src.

Whenever we have to clone any packages from GitHub, we clone them into the src folder.

Every time there is a new package installed, c++ file added, we need to run the following when in `~/catkin_ws` :

`catkin_make`

`source devel/setup.bash`

### Recommendation:

Use [terminator](https://www.geeksforgeeks.org/terminator-a-linux-terminal-emulator/) instead of terminal to use ROS as it would be convenient to use multiple terminals at one view. To install:

`sudo apt install terminator`

# Reference Links:

[http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment)

——————————————————————————————————————————-
