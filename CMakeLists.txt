cmake_minimum_required(VERSION 3.0)

project(demo01)

# 1.定义一些变量，使用方式和bash一样，${VAR}
# set(SRC_LIST function.h function.cpp main.cpp)
# 2.指定C++的版本，CMAKE_CXX_STANDARD应该是一个内置变量
set(CMAKE_CXX_STANDARD 11)
# 3.指定输出的路径
# set(OUTPUT_PATH,...)
# set(EXECUTABLE_OUTPUT_PATH ${OUTPUT_PATH}\bin)

# 搜索文件
# 方式一：使用aux_source_directory
# 第一个参数代表源文件目录名 第二个参数是一个变量，存储所有的源文件
aux_source_directory(${PROJECT_SOURCE_DIR} SRC_LIST)
# 方式二：使用
file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp)

add_executable(demo01 ${SRC_LIST})