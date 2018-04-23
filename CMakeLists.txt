cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
set(SFW_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include)

option(BUILD_SFW_EXAMPLE "build example application for SimpleFileWatcher" OFF)

project(simplefilewatcher VERSION 1.0 LANGUAGES CXX)
add_subdirectory("source")

if (BUILD_SFW_EXAMPLE)
    add_executable(sfw_test "SimpleDemo.cpp")
    target_link_libraries(sfw_test PUBLIC sfw_lib)
endif()
