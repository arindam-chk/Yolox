project(Yolox)
cmake_minimum_required(VERSION 3.0)
enable_testing()

add_library(Cogent STATIC
    Cogent/src/add.cc)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/Cogent/src)
add_executable(run_x86_64
    src/app.cc)
target_link_libraries(run_x86_64 Cogent)
