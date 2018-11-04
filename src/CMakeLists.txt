cmake_minimum_required(VERSION 3.12)
project(Calculator)

#version 1.0.0
set(Calculate_VERSION_MAJOR 1)
set(Calculate_VERSION_MINOR 0)

#configuration 
configure_file(
  "${PROJECT_SOURCE_DIR}/CalculateConfig.h.in"
  "${PROJECT_BINARY_DIR}/Calculate.h"
)

#Binary tree to include modules 
include_directories("${PROJECT_BINARY_DIR}")

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)

set(QT_VERSION "5.11.2")
set(CMAKE_PREFIX_PATH /Qt/${QT_VERSION}/mingw53_32/)
find_package(Qt5 COMPONENTS Widgets DBus REQUIRED)


add_executable(Calculate main.cxx)
#target_link_libraries(Calculate ${EXTRA_LIBS})
target_link_libraries(Calculate Qt5::Widgets)


install (TARGETS Calculate DESTINATION bin)
install (FILES "${PROJECT_BINARY_DIR}/Calculate.h"
        DESTINATION include)