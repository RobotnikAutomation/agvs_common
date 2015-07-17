cmake_minimum_required(VERSION 2.8.3)
project(agvs_description)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  message_runtime
  roscpp
  std_msgs
  std_srvs
  tf
)

catkin_package()

