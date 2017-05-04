cmake_minimum_required(VERSION 3.7)
project(OpenMPI)
add_executable(OpenMPI ${SOURCE_FILES} main.cpp)
find_package(MPI REQUIRED)
include_directories(${MPI_INCLUDE_PATH})

set(CMAKE_CXX_COMPILE_FLAGS ${CMAKE_CXX_COMPILE_FLAGS} ${MPI_COMPILE_FLAGS})
set(CMAKE_CXX_LINK_FLAGS ${CMAKE_CXX_LINK_FLAGS} ${MPI_LINK_FLAGS})
target_link_libraries(OpenMPI ${MPI_LIBRARIES})

set(SOURCE_FILES main.cpp)
