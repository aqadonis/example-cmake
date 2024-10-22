include_directories(${PROJECT_SOURCE_DIR}/libadd)
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
add_executable(MultipleDirs main.cpp)
target_link_libraries(MultipleDirs add)
