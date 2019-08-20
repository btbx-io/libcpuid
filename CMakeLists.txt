cmake_minimum_required(VERSION 3.1.0)

# Use newer policies if available, up to most recent tested version of CMake.
if(${CMAKE_VERSION} VERSION_LESS 3.11)
  cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
else()
  cmake_policy(VERSION 3.11)
endif()

project(libcpuid CXX)

file(GLOB LIBCPUID_SOURCES
        "${CMAKE_CURRENT_SOURCE_DIR}/libcpuid/*.h"
        "${CMAKE_CURRENT_SOURCE_DIR}/libcpuid/*.asm"
        "${CMAKE_CURRENT_SOURCE_DIR}/libcpuid/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/libcpuid/*.c"
        )

add_library(libcpuid ${LIBCPUID_SOURCES})
		
target_include_directories(libcpuid PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}/libcpuid>)

