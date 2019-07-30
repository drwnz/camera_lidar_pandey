cmake_minimum_required(VERSION 2.6 FATAL_ERROR)

project(mi-extrinsic-calib)

find_package(PCL 1.3 REQUIRED)

set (SRC
  main.cpp
  Calibration.cpp  Calibration.h
  Calibration_deprecated.cpp
  )
include_directories (${Glib_INCLUDE_DIRS}
  ${GSL_INCLUDE_DIR}
  ${OpenCV_INCLUDE_DIRS}
  ${PCL_INCLUDE_DIRS}
  ${SRC_DIR}/common
  )
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})


add_executable (mi-extrinsic-calib ${SRC})
target_link_libraries (mi-extrinsic-calib
  ${Glib_LIBRARIES}
  ${GSL_LIBRARIES}
  ${OpenCV_LIBRARIES}
  ${PCL_LIBRARIES}
  common
  )
