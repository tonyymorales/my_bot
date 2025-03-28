cmake_minimum_required(VERSION 3.5)
project(my_bot)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# Find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)

# If building tests, enable linting
if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

# Corrected install command
install(TARGETS 
  DESTINATION lib/${PROJECT_NAME}  # Specify the correct destination folder
)

# Optionally, install configuration or launch files
install(DIRECTORY config launch worlds
  DESTINATION share/${PROJECT_NAME}
)

ament_package()
