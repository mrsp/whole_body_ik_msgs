cmake_minimum_required(VERSION 3.5)
project(whole_body_ik_msgs)


find_package(catkin REQUIRED COMPONENTS
std_msgs
message_generation
actionlib
actionlib_msgs
geometry_msgs
nav_msgs
sensor_msgs
)

add_message_files(
DIRECTORY msg
FILES LinearTask.msg AngularTask.msg DOFTask.msg Task.msg
)
add_action_files(
  DIRECTORY action
  FILES Humanoid.action
)

generate_messages(
DEPENDENCIES
std_msgs
actionlib_msgs
geometry_msgs
nav_msgs
sensor_msgs
)

catkin_package( CATKIN_DEPENDS std_msgs geometry_msgs sensor_msgs nav_msgs message_runtime)
