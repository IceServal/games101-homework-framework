cmake_minimum_required(VERSION 3.10)
project(rasterizer3)

set(CMAKE_CXX_STANDARD 17)

include_directories(./../)
include_directories(./../opencv/include)

set(OpenCV_LIBRARIES ${PROJECT_SOURCE_DIR}/../opencv/lib/opencv_world455d.lib)
file(COPY ${PROJECT_SOURCE_DIR}/../opencv/bin/opencv_world455d.dll DESTINATION ${PROJECT_BINARY_DIR}/)

add_executable(rasterizer3 main.cpp rasterizer.cpp triangle.cpp texture.cpp)
target_link_libraries(rasterizer3 ${OpenCV_LIBRARIES})

file(COPY ${PROJECT_SOURCE_DIR}/models/ DESTINATION ${PROJECT_BINARY_DIR}/../models/)

