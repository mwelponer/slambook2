# 声明要求的 cmake 最低版本
cmake_minimum_required(VERSION 3.0.0)

# specifying a project name
project(HelloSLAM)

# set the build variant Degub/Release
set(CMAKE_BUILD_TYPE "Debug")

# A VERY SIMPLE PROGRAM
# specify an executable program
add_executable(helloSLAM helloSLAM.cpp)
# manually: now create the intermediate makefiles with % cmake .
# then compile using % make


# NOW TRY THE SAME BUT INTO A LIBRARY
# compile this file into a static library called “hello”
add_library(hello libHelloSLAM.cpp)
# static libraries will be compiled into .a files

# compile this file into a shared library called "hello_shared"
add_library(hello_shared SHARED libHelloSLAM.cpp)
# shared libraries are compiled into .so files

# to call the library you need a header .h file, so we write one

# now we write a program 
add_executable(useHello useHello.cpp)
# and we link the library: the “useHello” program can use the code 
# found inside the hello_shared library
target_link_libraries(useHello hello_shared)
