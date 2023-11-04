cmake_minimum_required(VERSION 3.5)
project(robotont_msgs)

# Find packages in ROS 2
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

# Specify message files
set(msg_files
  "msg/ColorRGB.msg"
  "msg/LedModulePixel.msg"
  "msg/LedModuleSegment.msg"
  "msg/PowerSupply.msg"
  "msg/LaserScanSplit.msg"
)

# Generate message files
rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  DEPENDENCIES std_msgs
)

# Create the package
ament_export_dependencies(rosidl_default_runtime)

ament_package()