cmake_minimum_required(VERSION 3.10)
project(jdredis C CXX)

set(CMAKE_CXX_STANDARD 11)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")
set(CUSTOM_ROOT $ENV{HOME}/.root2)
list(INSERT CMAKE_FIND_ROOT_PATH 0 ${CUSTOM_ROOT})

#find_package(Boost COMPONENTS thread system REQUIRED)
file(GLOB srcs
     RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}"
     *.c)
add_library(hiredis ${srcs})
target_include_directories(hiredis PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
add_subdirectory(examples)
