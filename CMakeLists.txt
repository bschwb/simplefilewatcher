cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
set(SFW_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include)
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

project(simplefilewatcher VERSION 1.0 LANGUAGES CXX)
add_subdirectory("source")

option(SFW_WITH_TEST "Build with demo app" off)
if (SFW_WITH_TEST)
    add_executable(sfw_test "SimpleDemo.cpp")
    target_link_libraries(sfw_test sfw_lib)
    include_directories(sfw_test ${SFW_INCLUDE_DIR})
endif()
