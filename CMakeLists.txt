cmake_minimum_required(VERSION 3.20)
project(homework8)

macro(print_all_variables)
    message(STATUS "print_all_variables------------------------------------------{")
    get_cmake_property(_variableNames VARIABLES)
    foreach (_variableName ${_variableNames})
        message(STATUS "${_variableName}=${${_variableName}}")
    endforeach()
    message(STATUS "print_all_variables------------------------------------------}")
endmacro()

set(CMAKE_CXX_STANDARD 17)
include(${CMAKE_SOURCE_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

#print_all_variables()

add_executable(homework8 main.cpp)
target_link_libraries(homework8 ${CONAN_LIBS})
target_include_directories(homework8 PRIVATE ${CONAN_INCLUDE_DIRS})
target_include_directories(homework8 PRIVATE ${CONAN_INCLUDE_DIRS_GTEST})
