# ROS Noetic Installation
ROS (Robot Operating System) provides libraries and tools to help software developers create robot applications. It provides hardware abstraction, device drivers, libraries, visualizers, message-passing, package management, and more. ROS is licensed under an open source, BSD license.

## Installation Steps
1. Setup your computer to accept software from packages.ros.org.

```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list' 
```
2. Set up your keys.
```bash
sudo apt install curl
```
```bash
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```
3. Make sure your Debian package index is up-to-date.
```bash
sudo apt update
```
4. Installing the ROS recommended configuration.
```bash
sudo apt install ros-noetic-desktop-full
```
## Configuration Steps
1. Adding environment variables: To Automatically add ROS environment variables to your bash session every time a new shell terminal/bash is launched, enter the following commands (this step is similar as adding environmental variable in windows).
```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
```
2. Sourcing bashrc ensures to use updated bashrc, or it can be done by re-opening new terminal.
```bash
source ~/.bashrc
```
## Additional Dependencies: To install this tool and other dependencies for building ROS packages.
Additional dependencies:

- python3-rosdep
- python3-rosinstall
- python3-rosinstall-generator
- python3-wstool
```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

- Initialize rosdep: Before you can use many ROS tools, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS. If you have not yet installed rosdep, do so as follows.
```bash
sudo apt install python3-rosdep
```

```bash
sudo rosdep init
```
Note: Do not use ‘sudo’ command in the next step, as it may result in different errors in later stages.
```bash
rosdep update
```
## Additional Installation
- Caktin tools
```bash
sudo apt-get install ros-noetic-catkin python3-catkin-tools
```
- Turtlesim
```bash
sudo apt-get install ros-noetic-ros-tutorials
```

Check installation
Run the below command on a new terminal after performing all the steps above, this will ensure that the ROS master is running perfectly on the system.
```bash
roscore
```

![1645186439720-image-20220218191357854](https://user-images.githubusercontent.com/92209922/196026909-5b4bccd6-f7fa-4021-90ff-c7ea8c8f890e.png)

This confirms that ROS master is running perfectly in the system and that ROS Noetic has been installed successfully.
