cmake_minimum_required(VERSION 3.19)
project(developer_joyofenergy_cpp)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_BINARY_DIR})
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "-fpermissive")
set(CMAKE_BUILD_TYPE "Debug")
add_definitions(-D_GLIBCXX_USE_CXX11_ABI=0)

add_subdirectory(rest)
add_executable(app main.cpp)
target_link_libraries(app PRIVATE rest pthread)

enable_testing()
add_subdirectory(test)