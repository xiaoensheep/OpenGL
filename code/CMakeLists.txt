cmake_minimum_required(VERSION 3.10)
project(OpenGLProjects)

set(CMAKE_CXX_STANDARD 11)

# 可执行文件
add_executable(learnshader ./2_shader/LearnShader.cpp /home/zxy/Development/OpenGL/glad/src/glad.c)
add_executable(textures ./3_Textures/texture.cpp /home/zxy/Development/OpenGL/glad/src/glad.c)

# 包含头文件目录
target_include_directories(learnshader PRIVATE
    /home/zxy/Development/OpenGL/glad/include
    /home/zxy/Development/OpenGL/code/2_shader
)
target_include_directories(textures PRIVATE
    /home/zxy/Development/OpenGL/glad/include
    /home/zxy/Development/OpenGL/code/Inc/
)

# 链接 OpenGL 和 GLFW
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

target_link_libraries(learnshader PRIVATE OpenGL::GL glfw)
target_link_libraries(textures   PRIVATE OpenGL::GL glfw)
