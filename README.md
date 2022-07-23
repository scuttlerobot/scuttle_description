# scuttle_description

Provides the geometric description of the SCUTTLE robot for use with
[RViz](http://wiki.ros.org/rviz), [Gazebo](https://gazebosim.org/) and other [ROS](https://ros.org)
nodes.

## Dependencies

The configurations in this repository assume you have the following prerequisites installed on the
device on which you want to run this code. That device might be an Ubuntu machine or a physical
SCUTTLE using Raspberry Pi OS.

1. [ROS Noetic](http://wiki.ros.org/noetic) with the `robot_state_publisher` and `joint_state_publisher`
   packages.
1. A working [ROS workspace](http://wiki.ros.org/catkin/Tutorials/create_a_workspace).


## Contents

This repository contains different folders for the different parts of the robot description.

* The URDF files that describe the SCUTTLE robot for ROS, RViz and Gazebo.
  * [urdf/scuttle.xacro](urdf/scuttle.xacro) - The geometric description of scuttle with the different
    [link](http://wiki.ros.org/urdf/XML/link) and [joint](http://wiki.ros.org/urdf/XML/joint)
    elements.
  * [urdf/scuttle.trans](urdf/scuttle.trans) - Contains the description of the different
    [actuators](http://wiki.ros.org/urdf/XML/Transmission) in SCUTTLE.
  * [urdf/materials.xacro](urdf/materials.xacro) - Specifies the material properties for Gazebo and Rviz
  * [urdf/scuttle.gazebo](urdf/scuttle.gazebo) - The Gazebo specific additions to the model, e.g.
    the [differential drive](https://classic.gazebosim.org/tutorials?tut=ros_gzplugins#DifferentialDrive)
    and the different sensors.
* The [meshes](meshes/) directory contains the STL mesh files for the different scuttle parts. Generally
  there will be a visual mesh and a collision mesh for each part.. The visual mesh is generally finer
  and more detailed.
* The [rviz](rviz/) directory contains the configuration file for RViz

## Usage

In general the `scuttle_description` package will not directly be launched. It is designed to be
referenced by other SCUTTLE ROS packages.

The most useful launch file is the [launch/rviz.launch] file which will launch RViz.
