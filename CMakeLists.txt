cmake_minimum_required(VERSION 3.28)
project(particle_sim C)

set(CMAKE_C_STANDARD 23)
set(OpenGlLinkers -lglut -lGLU -lGL)

set(CMAKE_MODULE_PATH /usr/local/lib/cmake)
set(CMAKE_PREFIX_PATH /usr/local/lib/cmake/glfw3)

find_package (PkgConfig REQUIRED)
find_package (OpenGL REQUIRED)
find_package (glfw3 REQUIRED)

include_directories(/usr/local/include glad)
include_directories(${GLFW_INCLUDE_DIRS})

set(SOURCE_FILES main.c)
add_executable(particle_sim ${SOURCE_FILES})
target_link_libraries (particle_sim
        ${OPENGL_LIBRARIES}
        ${GLFW3_LIBRARY} glfw)