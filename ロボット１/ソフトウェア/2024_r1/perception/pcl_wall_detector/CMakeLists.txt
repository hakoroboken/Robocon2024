cmake_minimum_required(VERSION 3.5)
project(pcl_wall_detector)

find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()

ament_auto_add_library(target_pcl_wall_detector SHARED
  DIRECTORY src
)

target_include_directories(target_pcl_wall_detector
  SYSTEM PUBLIC
)

rclcpp_components_register_node(target_pcl_wall_detector
  PLUGIN "pcl_wall_detector::PCLWallDetector"
  EXECUTABLE pcl_wall_detector_node
)

ament_auto_package(
  INSTALL_TO_SHARE
)