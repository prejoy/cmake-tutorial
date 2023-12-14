# TODO 1: Set the minimum required version of CMake to be 3.10
cmake_minimum_required(VERSION 3.26)
#================   upon  ====================

# TODO 2: Create a project named Tutorial
# project(Tutorial)
project(Tutorial VERSION 1.3)
#================   upon  ====================

# TODO 4 ：Specifying the C++ Standard
# TODO 6: Set the variable CMAKE_CXX_STANDARD to 11
#         and the variable CMAKE_CXX_STANDARD_REQUIRED to True
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)
#================   upon  ====================


# TODO 8: Use configure_file to configure and copy TutorialConfig.h.in to
#         TutorialConfig.h
configure_file(TutorialConfig.h.in TutorialConfig.h)
#================   upon  ====================


# TODO 3: Add an executable called Tutorial to the project
# Hint: Be sure to specify the source file as tutorial.cxx

set(SRC_LIST tutorial.cxx)
# 如果有多个源文件，之间使用空格隔开即可。
# set(SRC_LIST  a.cpp  b.cpp  c.cpp)

#add_executable(Tutorial ${SRC_LIST})
add_executable(${CMAKE_PROJECT_NAME} ${SRC_LIST})
#================   upon  ====================


# TODO 9: Use target_include_directories to include ${PROJECT_BINARY_DIR}
target_include_directories(Tutorial  PUBLIC  ${PROJECT_BINARY_DIR})
#================   upon  ====================

