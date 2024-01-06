cmake_minimum_required(VERSION 3.10)

project(CLOx C)

# Set C standard
set(CMAKE_C_STANDARD 11)

# Set the Clang compiler
set(CMAKE_C_COMPILER "clang")

# Add the source and include directories. if you define these,
# a CMakeLists.txt file must be present in the subdirectory.
# add_subdirectory(src)
# add_subdirectory(include)

# Add the executable
add_executable(clox src/main.c src/memory.c src/chunk.c src/debug.c src/value.c src/vm.c src/compiler.c src/scanner.c)

# Specify include directories
target_include_directories(clox PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Optionally, set Clang-specific compiler flags
target_compile_options(clox PRIVATE -Wall)
#target_compile_options(clox PRIVATE -Wall -Werror -Weverything)

# Generate compile_commands.json
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
