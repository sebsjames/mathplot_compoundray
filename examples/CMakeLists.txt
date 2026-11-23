add_executable(cube cube.cpp)
target_link_libraries(cube mathplot_examples)

# Eigen finding is not reliable on Github Mac OS runners
if(NOT APPLE)
  if(Eigen3_FOUND)
    add_executable(cubetrans cubetrans.cpp)
    target_include_directories (cubetrans BEFORE PRIVATE ${EIGEN3_INCLUDE_DIR})
    target_link_libraries(cubetrans mathplot_examples)
  endif(Eigen3_FOUND)
endif()

add_executable(cubetrans2 cubetrans2.cpp)
target_link_libraries(cubetrans2 mathplot_examples)

add_executable(curvytelly_pipe curvytelly_pipe.cpp)
target_link_libraries(curvytelly_pipe mathplot_examples)

add_executable(curvytelly_chequered_pipe curvytelly_chequered_pipe.cpp)
target_link_libraries(curvytelly_chequered_pipe mathplot_examples)
