cmake_minimum_required(VERSION 3.28)
project(GenerateStaticLibrary)

set(CMAKE_CXX_STANDARD 20)

add_library(add STATIC add.cpp)
add_executable(GenerateStaticLibrary main.cpp)
target_link_libraries(GenerateStaticLibrary add)
