cmake_minimum_required(VERSION 3.28)
project(GenerateDynamicLibrary)

set(CMAKE_CXX_STANDARD 20)

add_library(add SHARED add.cpp)
add_executable(GenerateDynamicLibrary main.cpp)
target_link_libraries(GenerateDynamicLibrary add)
