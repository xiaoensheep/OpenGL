cmake_minimum_required(VERSION 3.10)
project(OpenGLProjects)

set(CMAKE_CXX_STANDARD 11)

# 可执行文件
add_executable(LearnTrans /home/zxy/Development/OpenGL/code/4_Transformations/LearnTrans.cpp /home/zxy/Development/OpenGL/glad/src/glad.c)

# 包含头文件目录

target_include_directories(LearnTrans PRIVATE
    /home/zxy/Development/OpenGL/glm-1.0.2
    /home/zxy/Development/OpenGL/code/Inc
)

# 链接 OpenGL 和 GLFW
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

# target_link_libraries(LearnTrans PRIVATE OPENGL::GL glfw)
target_link_libraries(LearnTrans PRIVATE ${OPENGL_LIBRARIES} glfw)
include_directories(${OPENGL_INCLUDE_DIR})