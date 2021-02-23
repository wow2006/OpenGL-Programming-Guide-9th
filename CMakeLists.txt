# ${CMAKE_SOURCE_DIR}/CMakeLists.txt
cmake_minimum_required(VERSION 3.16)
project(vermilion9 C CXX)

include(${CMAKE_SOURCE_DIR}/cmake/download_file.cmake)
download_file(
  ${CMAKE_SOURCE_DIR}/media.tar.gz
  https://docs.google.com/uc?export=download&id=1T1alGwGGr8kSax_oouXx1F3Y1MeomI96
  de0ce5bb58030c07185f4244ad92c517
)
decompress(
  ${CMAKE_SOURCE_DIR}/media.tar.gz
  ${CMAKE_BINARY_DIR}/bin/
)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

find_package(glfw3  REQUIRED)
find_package(OpenGL REQUIRED)

add_subdirectory(thirdparty)
add_subdirectory(examples)

