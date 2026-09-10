cmake_minimum_required(VERSION 3.15)
project(Algorithms)

enable_testing()

set(CMAKE_COMPILE_WARNING_AS_ERROR ON)

if (MSVC)
    add_compile_options(/W4 /WX)
else()
    add_compile_options(-Wall -Wextra -Werror -Wpedantic -Wno-gnu-empty-struct -Wno-unused-parameter -ftrapv)
endif()

add_subdirectory(LibraryCPP)
add_subdirectory(Lab1CPP)