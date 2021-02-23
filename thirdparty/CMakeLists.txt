# ${CMAKE_SOURCE_DIR}/thirdparty/CMakeLists.txt
find_package(OpenMP)
if(OPENMP_FOUND)
  set(CMAKE_C_FLAGS   "${CMAKE_C_FLAGS} ${OpenMP_C_FLAGS}")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
endif()


add_library(
  vermilion
  STATIC
)

target_sources(
  vermilion
  PRIVATE
  src/gl3w.c
  src/LoadShaders.cpp
  src/targa.cpp
  src/vdds.cpp
  src/loadtexture.cpp
  src/vermilion.cpp
  src/vbm.cpp
)

target_include_directories(
  vermilion
  PUBLIC
  ${CMAKE_CURRENT_LIST_DIR}/include
)

target_link_libraries(
  vermilion
  PUBLIC
  glfw
  $<$<BOOL:${OpenMP_FOUND}>:OpenMP::OpenMP_CXX>
)

