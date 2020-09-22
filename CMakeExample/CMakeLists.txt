# CMakeList.txt : CMake project for CMakeExample, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Add our library
add_subdirectory("ExampleLibrary")

# Add source to this project's executable.
add_executable (CMakeExample "CMakeExample.cpp" "CMakeExample.h")
target_link_libraries(CMakeExample ExampleLibrary)

# TODO: Add tests and install targets if needed.
