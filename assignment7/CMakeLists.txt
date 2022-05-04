cmake_minimum_required(VERSION 3.10)
project(ray-tracing3)

set(CMAKE_CXX_STANDARD 17)

add_executable(ray-tracing3 main.cpp scene.cpp bvh.cpp renderer.cpp)

file(COPY ${PROJECT_SOURCE_DIR}/../opencv/bin/opencv_world455d.dll DESTINATION ${PROJECT_BINARY_DIR}/)
file(COPY ${PROJECT_SOURCE_DIR}/models/ DESTINATION ${PROJECT_BINARY_DIR}/../models/)

