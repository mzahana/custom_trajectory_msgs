cmake_minimum_required(VERSION 3.0.2)
project(custom_trajectory_msgs)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  message_generation
  nav_msgs
  sensor_msgs
  std_msgs
)


add_message_files(
  DIRECTORY msg
  FILES
  State.msg
  StateTrajectory.msg
)

generate_messages(DEPENDENCIES geometry_msgs std_msgs)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES trajectory_msgs
  CATKIN_DEPENDS geometry_msgs nav_msgs sensor_msgs std_msgs message_runtime
#  DEPENDS system_lib
)