# 0. Create Source and CMakeFile
# 1. mkdir build
# 2. cd build
# 3. cmake .. - Generating the Build Files / Configure the Project
# 4. cmake --build . - Building the Project
# 5. ./Executable - Running the Project

cmake_minimum_required(VERSION 3.22)

project(CppProjectTemplate VERSION 1.0.0 LANGUAGES C CXX)

add_library(Library STATIC my_lib.cc)

add_executable(Executable main.cc)

target_link_libraries(Executable PUBLIC Library)