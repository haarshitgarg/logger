# Set the minimum required version of CMake
cmake_minimum_required(VERSION 3.5)

# Define the project and its name
project(logger VERSION 1.0 LANGUAGES CXX)

# Specify the location of header files
include_directories(include)

# Add all the source files in the 'src' directory
file(GLOB SOURCES "src/*.cc")

# Create the library from the source files
add_library(logger ${SOURCES})

# Create a test directory and add an executable for testing
add_executable(LoggerTest test/main.cpp)
target_link_libraries(LoggerTest PRIVATE logger)

