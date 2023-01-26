# rosinante_description
This repository contains the (urdf) description files for ROSinante.

## /urdf

Contains complete configuration for ROSinante in [rosinante.urdf.xacro](urdf/rosinante.urdf.xacro). Pulls in all description files for rviz, gazebo and ros2_control.


## /gazebo
Contains a robot description for launching a basic simulation of ROSinante in Ignition Gazebo.

Uses [ignition::gazebo::systems::VelocityControl](https://gazebosim.org/api/gazebo/4.5/classignition_1_1gazebo_1_1systems_1_1VelocityControl.html) and [ignition::gazebo::systems::OdometryPublisher](https://gazebosim.org/api/gazebo/5.1/classignition_1_1gazebo_1_1systems_1_1OdometryPublisher.html). Additionally ros2_control can be integrated using [ign_ros2_control::IgnitionROS2ControlPlugin](https://github.com/ros-controls/gz_ros2_control) (not finished as of now).

## /ros2_control

Contains description for initialising ros2_control with fake or real hardware.

| Parameter |  Type  | Default value | Description |
|:-----|:--------:|:---:|:---|
| `use_fake_hardware` | bool | false | Start robot with fake hardware mirroring command to its states. |
| `serial_number` | hex | - | Serial number of the ODrive board to connect to in hexadecimal notation. No leading '0x'. |
| `json_descriptor_path` | string | - | File path in which to read/write the API-descriptor used by/for the ODrive. |
| `read_config` | bool | true | Set to true if API descriptor should be read from file instead of board. |
| `write_config` | bool | false | Set to true if API descriptor should be written to file. |


## /config
Contains basic rviz configuration for monitoring ROSinante.