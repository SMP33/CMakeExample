# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.8)

set (CMAKE_CXX_STANDARD 11)
project ("CMakeExample" CXX)

# Include sub-projects.cd .
add_subdirectory ("CMakeExample")

# You should comment out all the code below so that project files are generated for *nix too.
install(TARGETS
        ExampleLibrary
        EXPORT Targets
    ARCHIVE DESTINATION ${CMAKE_INSTALL_PREFIX}/lib
    LIBRARY DESTINATION ${CMAKE_INSTALL_PREFIX}/lib
    RUNTIME DESTINATION ${CMAKE_INSTALL_PREFIX}/bin
    INCLUDES DESTINATION ${CMAKE_INSTALL_PREFIX}/include
    PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_PREFIX}/include
)

install(EXPORT Targets
        FILE Targets.cmake
        NAMESPACE ExampleName::
        DESTINATION ${CMAKE_INSTALL_PREFIX}/lib/cmake/CPQUtils
         )

export(PACKAGE ExampleName)