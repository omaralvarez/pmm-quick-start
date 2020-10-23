cmake_minimum_required(VERSION 3.3)
project(glfw_test LANGUAGES CXX)

include(cmake/pmm.cmake)

pmm(VCPKG
    REVISION 2020.07
    REQUIRES glew glfw3
)

find_package(glfw3 REQUIRED)
find_package(GLEW REQUIRED)

add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries(${PROJECT_NAME} glfw GLEW::GLEW)