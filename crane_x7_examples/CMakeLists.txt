cmake_minimum_required(VERSION 2.8.3)
project(crane_x7_examples)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
  geometry_msgs
  message_generation
)

add_service_files(FILES ObstacleAvoidance.srv)
generate_messages(DEPENDENCIES std_msgs geometry_msgs)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if your package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES crane_x7_examples
 CATKIN_DEPENDS message_runtime
#  DEPENDS system_lib
)

###########
## Build ##
###########

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)


#############
## Install ##
#############

catkin_install_python(PROGRAMS
  scripts/cartesian_path_example.py
  scripts/crane_x7_pick_and_place_demo.py
  scripts/gripper_action_example.py
  scripts/joint_values_example.py
  scripts/joystick_example.py
  scripts/obstacle_avoidance_example.py
  scripts/obstacle_client.py
  scripts/pick_and_place_in_gazebo_example.py
  scripts/pose_groupstate_example.py
  scripts/preset_pid_gain_example.py
  scripts/servo_info_example.py
  scripts/teaching_example.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
