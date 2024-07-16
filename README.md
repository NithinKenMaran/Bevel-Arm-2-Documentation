# Bevel-Arm-2-Documentation

# Arm Control with Joystick

## Overview

This script controls the rover arm with input from a joystick.

## Python Packages Used

`std_msgs` and `sensor_msgs` are imported and used. 

## Code Overview

### Node Class

All functionality of the script is encapsulated in the `Node` class.

It contains:
- `run()` function to process and publish ROS messages to control the arm. 
- `createMsg()` function to encapsulate message creation before publishing to a topic.
- `joyCallback()` function to run when a joystick message is received.

### Initialization

Initializes the script as a ROS node with name `arm_drive`.

Subscribes to joystick on the topic `joy_arm`

Publishes to topic `stm_write`

### Message Creation:

The variable `msg` stores the message to be published. Its type is `Int32MultiArray`, used for multidimensional arrays.

`msg.layout` specifies how the data is structured. `msg.layout.dim` stores the dimensions of the array, using `MultiArrayDimension()` objects.

Dimensions have 2 properties: Size and Stride.

`size` specifies the number of elements in that particular dimension.

`stride` specifies the number of elements to skip to get to the next element of the current dimension.

The `msg.layout.dim.label` attribute stores the name of the layout.

