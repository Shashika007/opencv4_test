cmake_minimum_required(VERSION 3.10)
project(opencv4_test)

set(CMAKE_CXX_STANDARD 14)

set (CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH}
        /usr/local/opencv-4.0.0/share/OpenCV
        /usr/share/OpenCV)
set(OpenCV_DIR /home/te6000-16/opencv-4.0.0/build)
LIST(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/../../../cmake_modules)

set( OpenCV_FOUND 1 )

find_package(OpenCV REQUIRED)

include_directories(
        ${OpenCV_INCLUDE_DIRS}
)

set(LIBS
        ${OpenCV_LIBS}
        )

add_executable(opencv4_test main.cpp)

target_link_libraries(opencv4_test
        ${LIBS}
        )