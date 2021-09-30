cmake_minimum_required(VERSION 3.0.0)
project(one_demo VERSION 0.1.0)

include(CTest)
enable_testing()

add_executable(one_demo main.cpp)

find_package( OpenCV REQUIRED ) # locate OpenCV in system
include_directories( ${OpenCV_INCLUDE_DIRS} ) # provide library headers
target_link_libraries( one_demo ${OpenCV_LIBS} /usr/local/lib/libopencv_highgui.so.4.5.3) # link OpenCV libraries , hightgui.so not found by cmake so this hack
MESSAGE("OpenCV_LIBS: " ${OpenCV_LIBS} )  #display opencv libs found

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
