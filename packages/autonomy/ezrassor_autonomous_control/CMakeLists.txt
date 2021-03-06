# CMake installation file for the ezrassor_autonomous_control ROS package.
# Written by Cameron Taylor.
cmake_minimum_required(VERSION 2.8.3)
project(ezrassor_autonomous_control)
find_package(catkin REQUIRED COMPONENTS
    std_msgs
    rospy
    roscpp
)
catkin_python_setup()
catkin_package()
catkin_install_python(
    PROGRAMS
        nodes/obstacle_detection
        nodes/autonomous_control
        nodes/park_ranger
    DESTINATION
        ${CATKIN_PACKAGE_BIN_DESTINATION}
)
install(
    DIRECTORY
        launch/
    DESTINATION
        ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)
install(
    DIRECTORY
        config/
    DESTINATION
        ${CATKIN_PACKAGE_SHARE_DESTINATION}/config
)

install(
    DIRECTORY
        dem_data/
    DESTINATION
        ${CATKIN_PACKAGE_SHARE_DESTINATION}/dem_data
)

install(
    DIRECTORY
        weights_results/
    DESTINATION
        ${CATKIN_PACKAGE_SHARE_DESTINATION}/weights_results
)
