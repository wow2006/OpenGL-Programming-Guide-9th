# ${CMAKE_SOURCE_DIR}/CMakeLists.txt
cmake_minimum_required(VERSION 3.16)
project(vermilion9 C CXX)

file(
  COPY ${CMAKE_SOURCE_DIR}/media
  DESTINATION ${CMAKE_BINARY_DIR}/bin/
)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

find_package(glfw3  REQUIRED)
find_package(OpenGL REQUIRED)

add_subdirectory(thirdparty)
add_subdirectory(examples)

