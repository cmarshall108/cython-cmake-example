cmake_minimum_required(VERSION 2.8)
project(cmake_example)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

set(CMAKE_C_FLAGS "-Wall -Wextra")
set(CMAKE_C_FLAGS_DEBUG "-g")
set(CMAKE_C_FLAGS_RELEASE "-O3")

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_LIST_DIR}/cmake)
include(UseCython)

set(CYTHON_FLAGS ${CYTHON_FLAGS} -3)

FILE(GLOB SOURCE_FILES src/*.pyx)

add_subdirectory(src)
