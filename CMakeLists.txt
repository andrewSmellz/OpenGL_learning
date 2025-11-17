cmake_minimum_required(VERSION 4.0)
project(OpenGL_learning)

set(CMAKE_CXX_STANDARD 20)

# Include directories
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# Set MSYS2 path for GLFW
set(MSYS2_PATH "C:/msys64/mingw64")
include_directories(${MSYS2_PATH}/include)
link_directories(${MSYS2_PATH}/lib)

find_package(OpenGL REQUIRED)

# Add both main.cpp and glad.c
add_executable(OpenGL_learning main.cpp glad.c)

target_link_libraries(OpenGL_learning
        OpenGL::GL
        glfw3
        opengl32
        gdi32
)