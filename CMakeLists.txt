cmake_minimum_required(VERSION 3.10)

project(YourProjectName C)

# Set C standard
set(CMAKE_C_STANDARD 11)

# Set the Clang compiler
set(CMAKE_C_COMPILER "/path/to/clang")

# Add the source and include directories
add_subdirectory(src)
add_subdirectory(include)

# Add the executable
add_executable(your_executable_name src/main.c src/module1.c src/module2.c)

# Specify include directories
target_include_directories(your_executable_name PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Optionally, set Clang-specific compiler flags
target_compile_options(your_executable_name PRIVATE -Wall -Werror -Weverything)

# Generate compile_commands.json
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
