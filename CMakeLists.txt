cmake_minimum_required(VERSION 2.8)
project(console_bridge)

find_package(catkin REQUIRED)

# What is published by the 'console_bridge package'
catkin_package(
  INCLUDE_DIRS src
  LIBRARIES console_bridge
)

#Include sources directory
include_directories(include)

#Sources files
set(SOURCES
    src/console.cpp
)

#Enable C++11
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
#Enable compiler Warning
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -W -Wall")

#Build Server and Client as shared library
add_library(console_bridge SHARED ${SOURCES})
