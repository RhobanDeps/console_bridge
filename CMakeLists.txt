cmake_minimum_required(VERSION 3.16.3)
project(console_bridge)


#Sources files
set(SOURCES
    src/console.cpp
)

#Enable C++17
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17")
#Enable compiler Warning
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -W -Wall")

#Build Server and Client as shared library
add_library(console_bridge SHARED ${SOURCES})
#Include sources directory
target_include_directories(console_bridge PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
)
