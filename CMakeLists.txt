cmake_minimum_required(VERSION 3.21 FATAL_ERROR)

# for clangd NOTE: CMAKE_CXX_STANDARD is set globally so that it properly
# propagates to compile_commands.json
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(Volkmold)

add_subdirectory("volk" EXCLUDE_FROM_ALL)
add_executable(Volkmold "main.cpp")
target_link_libraries(Volkmold PRIVATE volk_headers)
