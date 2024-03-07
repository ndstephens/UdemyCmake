# 0. Create Source and CMakeFile
# 1. ~ $ mkdir build
# 2. ~ $ cd build
# 3. ~/build $ cmake .. - Generating the Build Files / Configure the Project
# 4. ~/build $ cmake --build . - Building the Project
# 5. ~/build $ ./Executable - Running the Project

# or

# 0. Create Source and CMakeFile
# 1. ~ $ mkdir build
# 2. ~ $ cmake -S . -B build - Generating the Build Files / Configure the Project
# 3. ~ $ cmake --build build - Building the Project
# 4. ~ $ ./build/Executable - Running the Project

cmake_minimum_required(VERSION 3.22)

# set the project name and version
# CppProjectTemplate is the name of the project
project(CppProjectTemplate VERSION 1.0.0 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD          17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS        OFF)

set(LIBRARY_NAME Library)
set(EXECUTABLE_NAME Executable)

option(COMPILE_EXECUTABLE "Whether to compile the executable" ON)
# ~/build $ cmake .. -DCOMPILE_EXECUTABLE=ON

add_subdirectory(configured)
add_subdirectory(src)

if (COMPILE_EXECUTABLE)
    add_subdirectory(app)
else()
    message("Without executable compiling")
endif()

