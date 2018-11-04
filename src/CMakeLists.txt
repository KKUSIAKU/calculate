cmake_minimum_required(VERSION 3.12)
project(Calculator)

#version 1.0.0
set(Tutorial_VERSION_MAJOR 1)
set(Tutorial_VERSION_MINOR 0)

#configuration 
configure_file(
  "${PROJECT_SOURCE_DIR}/CalculateConfig.h.in"
  "${PROJECT_BINARY_DIR}/Calculate.h"
)

#Binary tree to include modules 
include_directories("${PROJECT_BINARY_DIR}")


add_executable(Calculate main.cxx)
target_link_libraries(Calculate ${EXTRA_LIBS})