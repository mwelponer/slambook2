cmake_minimum_required(VERSION 3.0.0)
project(useEigen)

set(CMAKE_BUILD_TYPE "Release")
set(CMAKE_CXX_FLAGS "-O3")

# Add header file: Eigen library only has header files, we don’t need to link 
# the program to the library with the target_link_libraries statement.
# doc at http://eigen.tuxfamily.org/dox-devel/modules.html 
include_directories("/usr/local/include/eigen3")
add_executable(eigenMatrix eigenMatrix.cpp)
