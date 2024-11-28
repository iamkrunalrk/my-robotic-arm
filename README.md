# Environment Setup

## Detailed Instructions on Setting Up ROS and CoppeliaSim
To successfully implement the robotic arm project, the following environment setup is required:
**Prerequisites:**
Operating System: Ubuntu 20.04
ROS Version: Noetic
CoppeliaSim Version: 4.1.0 Edu
ROS DarkNet

**ROS Setup:**
Install ROS Noetic: Follow the official ROS installation guide for Ubuntu 20.04. This can be done using the following commands:
```
sudo apt update
sudo apt install ros-noetic-desktop-full
```

**Initialize rosdep:**
```
sudo rosdep init
rosdep update
```

**Create a Catkin Workspace:**
```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
```

**Clone Required Packages:**
```
Clone the darknet_ros repository for YOLOv3:
cd ~/catkin_ws/src
git clone --recursive -b updated https://github.com/iamkrunalrk/darknet_ros.git
```

**Build the workspace:**
```
cd ~/catkin_ws
catkin_make
```

Clone the gp7_visualization package for the Yaskawa GP7 robotic arm:
```
git clone https://github.com/iamkrunalrk/gp7_visualization.git
```

Clone the main repository containing the robotic arm control logic:
```
git clone https://github.com/iamkrunalrk/my-robotic-arm.git
```

Finally, build the packages:
```
cd ~/catkin_ws
catkin_make --only-pkg-with-deps my_robotic_arm gp7_visualization
```

Source the Workspace:
```
source ~/catkin_ws/devel/setup.bash
```

CoppeliaSim Setup
Download CoppeliaSim: Go to the CoppeliaSim download page and download the version for Ubuntu 20.04.

Extract and Run CoppeliaSim:
```
tar -xvf CoppeliaSim_Edu_V4_3_0_rev12_Ubuntu20_04.tar.xz
cd CoppeliaSim_Edu_V4_3_0_rev12_Ubuntu20_04
./coppeliaSim.sh
```

Install the ROS Interface Plugin:
Clone the sim_ros_interface package:
```
cd ~/catkin_ws/src
git clone https://github.com/CoppeliaRobotics/simROS.git sim_ros_interface
```

Modify the messages.txt file to add rospy_tutorials/Floats as the first line.
Compile the package:
```
cd ~/catkin_ws
catkin_make --only-pkg-with-deps sim_ros_interface
```

## Installation of Required Packages:

The following packages are essential for the project:
-Darknet ROS: For implementing the YOLOv3 object detection algorithm.
- CoppeliaSim: For simulating the robotic arm's movements and interactions.
- gp7_visualization: Contains the models and descriptions for the Yaskawa GP7 arm.

Each package can be installed as described in the previous sections.

