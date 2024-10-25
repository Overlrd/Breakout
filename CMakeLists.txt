# Set the minimum CMake version required
cmake_minimum_required(VERSION 3.10)

# Define the project name and specify the C++ standard
project(Breakout)
set(CMAKE_CXX_STANDARD 14)

# Include directories
include_directories(include)

# Define the source files
set(SOURCES
    breakout.cpp
    game.cpp
    glad.c
    resource_manager.cpp
    shader.cpp
    texture.cpp
)

# Add the executable target
add_executable(breakout ${SOURCES})

# Link additional libraries
find_package(OpenGL REQUIRED)
target_link_libraries(breakout ${OPENGL_LIBRARIES} glfw GL X11 pthread Xrandr Xi dl)
