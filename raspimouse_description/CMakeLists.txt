cmake_minimum_required(VERSION 2.8.3)
project(raspimouse_description)

find_package(catkin REQUIRED COMPONENTS
  rospy
  roscpp
  std_msgs
  std_srvs
  message_generation
  actionlib_msgs
  tf2_ros
  urdf
)

## Generate messages in the 'msg' folder
add_message_files(
  FILES
  LightSensorValues.msg
  LedValues.msg
  ButtonValues.msg
  MotorFreqs.msg
)

## Generate services in the 'srv' folder
add_service_files(
  FILES
  TimedMotion.srv
)

## Generate actions in the 'action' folder
add_action_files(
  FILES
  Music.action
)

generate_messages(
  DEPENDENCIES
  actionlib_msgs
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS rospy std_msgs std_srvs message_runtime
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

foreach(dir launch meshes urdf)
  install(DIRECTORY ${dir}/
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir}
  )
endforeach(dir)
