cmake_minimum_required(VERSION 3.10.0)
project(cdandan VERSION 0.1.0 LANGUAGES C)

set(CMAKE_C_COMPILER clang)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_compile_options(-Wall -Wextra)

# link to sanitizer when debugging
add_compile_options($<$<CONFIG:Debug>:-fsanitize=address> $<$<CONFIG:Debug>:-fno-omit-frame-pointer>)
add_link_options($<$<CONFIG:Debug>:-fsanitize=address>)

add_executable(cdandan main.c)

