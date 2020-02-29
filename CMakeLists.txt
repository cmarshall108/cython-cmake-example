cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
project(cmake_example)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Debug)
endif()

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)

set(CMAKE_C_FLAGS "-Wall")
set(CMAKE_C_FLAGS_DEBUG "-g")
set(CMAKE_C_FLAGS_RELEASE "-O3")

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_LIST_DIR}/cmake)
include(UseCython)

set(CYTHON_FLAGS ${CYTHON_FLAGS} -3)

FILE(GLOB SOURCE_FILES src/*.pyx)

add_subdirectory(src)
