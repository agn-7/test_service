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

catkin_install_python(PROGRAMS
  scripts/client.py
  scripts/server.py
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/scripts
)

install(FILES
  ./README.md
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
