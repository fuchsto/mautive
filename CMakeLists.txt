cmake_minimum_required(VERSION 3.13)

project(mautive
    VERSION 0.1.0
    DESCRIPTION "Library for model-based goal-oriented automation based on state charts"
    LANGUAGES CXX)

set(Progname "mautive")`

set(Boost_USE_STATIC_LIBS ON)
set(Boost_USE_MULTITHREADED OFF)
set(Boost_USE_STATIC_RUNTIME ON)

find_package(Boost 1.4.0 REQUIRED COMPONENTS statechart graph)

set MAUTIVE_SOURCES = "mautive.h mautive.cpp"

if(Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIRS})
    add_executable(${Progname} ${MOTIVE_SOURCES})
    target_link_libraries(${Progname} ${Boost_LIBRARIES})
endif()

set(CMAKE_CXX_STANDARD 14)

set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

include(GNUInstallDirs)

include(CTest)

add_subdirectory(src)
add_subdirectory(test)
