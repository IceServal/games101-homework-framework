cmake_minimum_required(VERSION 3.10)
project(bezier-curve)
set(CMAKE_CXX_STANDARD 14)

include_directories(./../)
include_directories(./../opencv/include)

set(OpenCV_LIBRARIES ${PROJECT_SOURCE_DIR}/../opencv/lib/opencv_world455d.lib)
file(COPY ${PROJECT_SOURCE_DIR}/../opencv/bin/opencv_world455d.dll DESTINATION ${PROJECT_BINARY_DIR}/)

add_executable(bezier-curve main.cpp)

target_link_libraries(bezier-curve ${OpenCV_LIBRARIES})

