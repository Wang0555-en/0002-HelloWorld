cmake_minimum_required(VERSION 3.20)

# 获取当前项目文件夹的名字
get_filename_component(PROJECT_NAME "${CMAKE_CURRENT_SOURCE_DIR}" NAME)

# 把项目名中的空格等特殊字符替换成 _
string(REGEX REPLACE "[^A-Za-z0-9_.-]" "_" PROJECT_NAME "${PROJECT_NAME}")

project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 自动获取 src 中所有 .cpp 文件
file(GLOB SRC_FILES CONFIGURE_DEPENDS
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
)

add_executable(${PROJECT_NAME} ${SRC_FILES})