cmake_minimum_required(VERSION 3.1)
project(game.libretro.thepowdertoy)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(THEPOWDERTOY_LIB NAMES thepowdertoy_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(THEPOWDERTOY_CUSTOM_BINARY ${THEPOWDERTOY_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} THEPOWDERTOY "")

include(CPack)
