cmake

cmake_minimum_required(VERSION 3.10)
project(Frog3D)

# Set C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add source files
add_executable(Frog3D main.cpp glad.c)

# Include directories
target_include_directories(Frog3D PRIVATE ${CMAKE_SOURCE_DIR}/include)

# Find GLFW (manual path since we're using precompiled binaries)
set(GLFW_LIBRARY ${CMAKE_SOURCE_DIR}/lib/glfw3.lib)
target_link_libraries(Frog3D PRIVATE ${GLFW_LIBRARY})

# Link Windows libraries
target_link_libraries(Frog3D PRIVATE opengl32.lib user32.lib gdi32.lib shell32.lib uuid.lib)

