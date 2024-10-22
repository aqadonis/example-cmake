cmake_minimum_required(VERSION 3.28)
project(MultipleFiles)

set(CMAKE_CXX_STANDARD 20)

set(SRC_LIST main.cpp add.cpp)

add_executable(MultipleFiles ${SRC_LIST})
