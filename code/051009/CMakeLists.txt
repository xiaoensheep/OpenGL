cmake_minimum_required(VERSION 3.10)
project(LearnOpenGL)

set(CMAKE_CXX_STANDARD 11)

add_executable(main2 main2.cpp)

# 加入 GLAD 源码
target_sources(main2 PRIVATE /home/zxy/Development/OpenGL/glad/src/glad.c)

# 包含 GLAD 的头文件目录
target_include_directories(main2 PRIVATE /home/zxy/Development/OpenGL/glad)

# 链接 OpenGL 和 GLFW
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

target_link_libraries(main2
    OpenGL::GL
    glfw
)
