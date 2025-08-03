---
layout: project
title: "Getting started with ROS2"
description: "Learning ROS robotic framework"
image: /assets/img/ros2/ros2_nav.png
permalink: /ros2/
---

# Developing an Autonomous Guided Vehicle (AGV) with ROS2: A Maker's Journey

![ROS2_NAV](/assets/img/ros2/ros2_nav.png)

My latest project involved the comprehensive design and implementation of an Automated Guided Vehicle (AGV) prototype, primarily intended for internal logistics applications within a corporate environment. This endeavor aimed to create an autonomous robot capable of robust trajectory planning and execution, precise spatial orientation within a confined setting, and intuitive control via a web-based interface.

The core of this prototype is built upon the iRobot Create 3 mobile robotics platform. To achieve its autonomous capabilities, I integrated several key hardware components:
* An **RPLIDAR A1 2D 360º** provides the necessary two-dimensional vision for environmental sensing. 
* A **Raspberry Pi 3B+** is responsible for transmitting the LiDAR data. 
* A **Linux-based computer** serves as the central processing unit, handling all data interpretation and decision-making. 
* A **router** acts as the communication hub, interconnecting all elements. 

On the software front, the project leverages **ROS 2 Galactic Geochelone** as its foundational robotics platform. I utilized `slam_toolbox` for effective cartography and `nav2` for advanced localization and navigation functionalities. To ensure user-friendly interaction, I developed a web interface using **Node.js** and `rclnodejs` for basic control of the prototype. 

This prototype achieves a Level 6 autonomy as an AGV/AMR, aligning with the ALFUS model. While it operates as a semi-autonomous system, I designed the web interface to allow an operator to command new trajectories, providing a crucial human-in-the-loop control mechanism. The robot successfully demonstrates the ability to autonomously navigate, generate and follow predetermined paths, orient itself within its physical space, and even avoid obstacles and respond to emergency stop commands.

A notable aspect of this project is its contribution to the existing literature, particularly as one of the few works that extensively utilizes ROS 2, especially within its navigation package. My operational procedure involves initial power-up, manual map generation via the web interface's joystick, map saving, and then initiating autonomous or manual navigation modes through the web interface, with visual feedback provided by RVIZ2. This project exemplifies the practical application of cutting-edge robotics software and hardware in creating functional autonomous systems.

[Complete project here](https://www.academia.edu/125034170/Prototipo_de_AGV_mediante_ROS2)

---
