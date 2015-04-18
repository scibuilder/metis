cmake_minimum_required(VERSION 2.8)
project(METIS)

set(GKLIB_PATH ${CMAKE_CURRENT_SOURCE_DIR}/GKlib CACHE PATH "path to GKlib")
option(BUILD_SHARED_LIBS "build a shared library" OFF)

include(${GKLIB_PATH}/GKlibSystem.cmake)
# Add include directories.
include_directories(${GKLIB_PATH})
include_directories(include)
# Recursively look for CMakeLists.txt in subdirs.
add_subdirectory("include")
add_subdirectory("libmetis")
add_subdirectory("programs")
