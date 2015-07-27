cmake_minimum_required(VERSION 2.8.3)
project(agvs_pad)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  std_msgs
  sensor_msgs  
  diagnostic_msgs
  diagnostic_updater
  robotnik_msgs
  ackermann_msgs
  std_srvs
)

catkin_package(

  CATKIN_DEPENDS robotnik_msgs ackermann_msgs 

)

###########
## Build ##
###########

include_directories(
  ${catkin_INCLUDE_DIRS}
)


## Declare a cpp executable
add_executable(agvs_pad_node src/agvs_pad_node.cpp)

## Add cmake target dependencies of the executable/library
## as an example, message headers may need to be generated before nodes
add_dependencies(agvs_pad_node robotnik_msgs_generate_messages_cpp)

## Specify libraries to link a library or executable target against
target_link_libraries(agvs_pad_node
   ${catkin_LIBRARIES}
 )

install(
  TARGETS agvs_pad_node
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
