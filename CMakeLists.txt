cmake_minimum_required(VERSION 3.5)

project(gazebo_tricycle_plugins)

set(CMAKE_CXX_STANDARD 17)

find_package(catkin REQUIRED COMPONENTS
 roscpp
 rospy
 std_msgs
 geometry_msgs
 sensor_msgs
 gazebo_plugins
)
find_package(gazebo REQUIRED)
find_package(roslaunch)

link_directories(${GAZEBO_LIBRARY_DIRS})
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}")

catkin_package(
	CATKIN_DEPENDS roscpp rospy std_msgs
	LIBRARIES
	TricycleDriveModPlugin
)

include_directories(
	include
	${catkin_INCLUDE_DIRS}
	${GAZEBO_INCLUDE_DIRS}
)

add_library(TricycleDriveModPlugin SHARED src/TricycleDriveModPlugin.cpp)
target_link_libraries(TricycleDriveModPlugin ${Boost_LIBRARIES} ${catkin_LIBRARIES} ${GAZEBO_LIBRARIES})



