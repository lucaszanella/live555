cmake_minimum_required(VERSION 2.8)

#g++ openRTSP.cpp -I. -I ../liveMedia/include -I ../groupsock/include -I ../UsageEnvironment/include ../liveMedia/libliveMedia.so -o openRTSP
project(liveMedia)

SET(GCC_COVERAGE_COMPILE_FLAGS "-fpermissive") #Why is this needed?
add_definitions(${GCC_COVERAGE_COMPILE_FLAGS})

include_directories(include)
include_directories(.)
include_directories(../UsageEnvironment/include)
include_directories(../groupsock/include)

add_definitions(-DXLOCALE_NOT_USED)

file(GLOB SOURCES "*.cpp" "*.c") 

add_library(liveMedia SHARED ${SOURCES})
