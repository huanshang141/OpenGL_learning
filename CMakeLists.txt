cmake_minimum_required(VERSION 3.28)
# 如果支持，请为 MSVC 编译器启用热重载。
if (POLICY CMP0141)
    cmake_policy(SET CMP0141 NEW)
    set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project(OpenGL)
include_directories("D:/WorkSpace/Clion_project/OpenGL/include")
link_directories("D:/WorkSpace/Clion_project/OpenGL/lib/GLFW")

set(CMAKE_CXX_STANDARD 17)

add_executable(OpenGL main.cpp
        glad.c)
target_link_libraries(OpenGL glfw3.lib)