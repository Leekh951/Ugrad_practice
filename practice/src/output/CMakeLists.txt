cmake_minimum_required(VERSION 3.0.2)
project(output)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Suppress PCL developer warnings
set(CMAKE_SUPPRESS_DEVELOPER_WARNINGS 1)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
)

# Include directories
include_directories(
  include
)

# Link directories
link_directories(
)

# Add custom messages
# add_message_files(
#   DIRECTORY msg
#   FILES
# )  

# generate_messages(
#    DEPENDENCIES
#    std_msgs
#    sensor_msgs
#    nav_msgs
#    geometry_msgs
# )

# Catkin package
catkin_package(
  CATKIN_DEPENDS message_runtime roscpp std_msgs 
)


# Install launch files
install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

# Add executables and link libraries
add_executable(output_node src/1.cpp)
target_link_libraries(output_node
  ${catkin_LIBRARIES}
)

