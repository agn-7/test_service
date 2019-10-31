cmake_minimum_required(VERSION 2.8.3)
project(test_service)


find_package(catkin REQUIRED COMPONENTS
  rospy
  message_generation
)


add_service_files(
  FILES
  MySrvFile.srv
)

generate_messages(
  DEPENDENCIES
)

catkin_package(CATKIN_DEPENDS message_runtime)

include_directories(
  ${catkin_INCLUDE_DIRS}
)


