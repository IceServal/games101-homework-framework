cmake_minimum_required(VERSION 3.10)
project(ray-tracing1)

set(CMAKE_CXX_STANDARD 17)

add_executable(ray-tracing1 main.cpp scene.cpp renderer.cpp)

target_compile_options(ray-tracing1 PUBLIC -Wall -pedantic -fsanitize=undefined)
target_compile_features(ray-tracing1 PUBLIC cxx_std_17)
target_link_libraries(ray-tracing1 PUBLIC -fsanitize=undefined)

