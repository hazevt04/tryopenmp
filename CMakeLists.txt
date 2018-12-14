cmake_minimum_required( VERSION 2.8.9 )

project( tryopenmp )

find_package(OpenMP)
if (OPENMP_FOUND)
    set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${OpenMP_C_FLAGS}")
    set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
    set (CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} ${OpenMP_EXE_LINKER_FLAGS}")
endif()

include_directories( $CMAKE_SOURCE_DIR )

add_definitions( -std=c++11 )

add_executable( tryopenmp tryopenmp.cpp )

#target_link_libraries( testStatePattern gsl gslcblas png z m )

