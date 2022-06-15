# cmake version
cmake_minimum_required(VERSION 3.10)

# project name
project(CppUTest CXX)

# C++ 11 standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# take respectives flags for debuf & release process
set(CMAKE_CXX_FLAGS_DEBUG_INIT "-std=c++11 -g -fno-omit-frame-pointer")
set(CMAKE_CXX_FLAGS_RELEASE_INIT "-std=c++11 -g -02")

# default build type : Debug
if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Debug)
endif()

# include path
include_directories(src)

# add subdirectory then find the CMakeLists.txt to execute
add_subdirectory(src)

# enable test and add test source
enable_testing()
add_subdirectory(test)

# add googletest library source
add_subdirectory(lib/googletest)