# ${CMAKE_SOURCE_DIR}/examples/CMakeLists.txt
set(
  EXAMPLES
  01-keypress
  01-triangles
  03-drawcommands
  03-instancing
  03-instancing2
  03-instancing3
  03-pointsprites
  03-primitiverestart
  03-xfb
  04-gouraud
  04-gouraud-float
  04-shadowmap
  06-cubemap
  06-load-texture
  06-mipfilters
  06-multitexture
  06-statictexture
  06-texturewrapping
  06-volumetexturing
  08-lightmodels
  09-simpletess
  09-teapot
  10-draw-xfb
  10-fur
  10-viewport-array
  11-doublewrite
  11-oit
  11-overdrawcount
  12-imageprocessing
  12-particlesimulator
  12-raytracer
  #12-simplecompute
)

foreach(EXAMPLE IN LISTS EXAMPLES)
  add_executable(
    ${EXAMPLE}
    WIN32
    ${EXAMPLE}/${EXAMPLE}.cpp
  )

  target_link_libraries(
    ${EXAMPLE}
    PUBLIC
    OpenGL::GL
    vermilion
    ${CMAKE_DL_LIBS}
  )
endforeach()

if(${CMAKE_SYSTEM_NAME} MATCHES "Linux")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -D_LINUX")
endif()


