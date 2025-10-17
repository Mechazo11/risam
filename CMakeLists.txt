project(robust-inference CXX C)
cmake_minimum_required(VERSION 3.5)

message(STATUS "================  ROBUST-INFERENCE  ======================")

# To avoid conflict with ROS 2's GTSAM which may be a later version of GTSAM 4.2
set(GTSAM_DIR "/usr/local/lib/cmake/GTSAM")
set(GTSAM_INCLUDE_DIR "/usr/local/include")
set(CMAKE_PREFIX_PATH "/usr/local" ${CMAKE_PREFIX_PATH})
find_package(GTSAM REQUIRED)
include_directories(${GTSAM_INCLUDE_DIR})

# build riSAM
add_subdirectory(risam)

# Build Experiments directory
add_subdirectory(experiments)
