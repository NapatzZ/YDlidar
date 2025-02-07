# YDLIDAR ROS2 Driver Installation Guide

This guide provides step-by-step instructions on how to install and set up the YDLIDAR ROS2 driver on ROS2 Humble.

## Prerequisites

Ensure that you have the following installed on your system:

- **Ubuntu 22.04** (or the appropriate OS for ROS2 Humble)
- **ROS2 Humble** installed and sourced
- **Git** and **colcon** installed

## Installation Steps

### 1. Create a Workspace

Open a terminal and create a workspace for the YDLIDAR ROS2 driver:

```bash
mkdir -p ~/ydlidar_ros2_ws/src
cd ~/ydlidar_ros2_ws/src
```
Clone the YDLIDAR ROS2 driver repository:

```bash
git clone -b humble https://github.com/YDLIDAR/ydlidar_ros2_driver.git
```
### 2. Build the ydlidar_ros2_driver Package
Navigate to the workspace directory:
```bash
cd ~/ydlidar_ros2_ws
```
Build the package using colcon:
```bash
colcon build --symlink-install
```
Source the setup file:
```bash
source ./install/setup.bash
```
## Testing the Installation
To verify that the YDLIDAR driver is installed correctly, launch the test node:
```bash
ros2 launch ydlidar_ros2_driver ydlidar_launch_view.py
```
If everything is set up properly, you should see lidar scan data in RViz or in the terminal output.

## Additional Notes
Ensure that the YDLIDAR device is properly connected via USB.
If permissions issues occur, try adding your user to the dialout group:
```bash
sudo usermod -aG dialout $USER
reboot
```
If errors occur during build, verify that all dependencies are installed and sourced correctly.
