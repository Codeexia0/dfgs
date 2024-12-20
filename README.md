ArUco Marker Robot Control with ROS2

This project demonstrates a ROS2-based robot control system using a TurtleBot simulated in Gazebo. The robot's movement is determined by the position of an ArUco marker detected in the camera feed. The system integrates a USB camera driver, custom nodes for marker detection, and logic to control the robot's movement.

Features

Camera Integration: Uses the usb_cam package to capture video from a built-in or external camera.

ArUco Marker Detection: Detects markers in the video feed and determines their position relative to the camera's field of view.

Robot Control: Moves the robot:

Forward: When the marker is in the top half of the image.

Backward: When the marker is in the bottom half of the image.

Gazebo Simulation: Simulates the robot and environment for testing.

Requirements

ROS2 (Humble or later recommended)

Gazebo

usb_cam ROS2 package

OpenCV (for ArUco marker detection)

Installation

Clone this repository:

git clone https://github.com/yourusername/aruco_marker_robot_control.git
cd aruco_marker_robot_control

Build the ROS2 workspace:

colcon build
source install/setup.bash

Install dependencies:

sudo apt install ros-<ros2-distro>-usb-cam
sudo apt install ros-<ros2-distro>-gazebo-ros
sudo apt install python3-opencv

Usage

Launch the Camera Driver
Start the camera driver to capture the video feed:

ros2 launch usb_cam usb_cam.launch.py

Run the Custom Node
Run the node to process the video feed and detect ArUco markers:

ros2 run aruco_marker_robot_control camera_subscriber

Launch the Robot in Gazebo
Start the Gazebo simulation environment:

ros2 launch aruco_marker_robot_control robot_sim.launch.py

Demonstration



Click the image above to watch the demonstration video: "ArUco Marker Robot Control with ROS2".

Files

camera_subscriber.py: Custom node for processing the camera feed and controlling the robot.

robot_sim.launch.py: Launch file for simulating the robot in Gazebo.

usb_cam.launch.py: Launch file for starting the camera driver.
