cmake_minimum_required(VERSION 3.10)
project(OpenGLProjects)

set(CMAKE_CXX_STANDARD 11)

add_executable(LearnColors /home/zxy/Development/OpenGL/code/7_Colors/LearnColors.cpp /home/zxy/Development/OpenGL/glad/src/glad.c)

target_include_directories(LearnColors PRIVATE
    /home/zxy/Development/OpenGL/glm-1.0.2
    /home/zxy/Development/OpenGL/code/Inc
)

find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

target_link_libraries(LearnColors PRIVATE ${OPENGL_LIBRARIES} glfw)
include_directories(${OPENGL_INCLUDE_DIR})