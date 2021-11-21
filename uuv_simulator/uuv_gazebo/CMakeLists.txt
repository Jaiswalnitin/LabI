cmake_minimum_required(VERSION 2.8.3)
project(uuv_gazebo)

find_package(catkin REQUIRED)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES uuv_gazebo
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

install(DIRECTORY rviz launch config
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
        PATTERN "*~" EXCLUDE)


catkin_install_python(PROGRAMS scripts/thrusters.py scripts/teleop_forces_torques.py
                      DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
