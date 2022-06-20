project(Yolox)
cmake_minimum_required(VERSION 3.0)
enable_testing()

#####################################################################################
include(ExternalProject)
ExternalProject_Add(Cogent
    SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/modules/Cogent
    PREFIX ${CMAKE_CURRENT_BINARY_DIR}/Cogent
    INSTALL_COMMAND ""
    )

ExternalProject_Get_Property(Cogent source_dir binary_dir)
#####################################################################################

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/modules/Cogent/src)
add_executable(run_x86_64
    src/app.cc)
target_link_libraries(run_x86_64 ${CMAKE_CURRENT_BINARY_DIR}/Cogent/src/Cogent-build/libCogent.a)
