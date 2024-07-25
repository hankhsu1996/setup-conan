cmake_minimum_required(VERSION 3.15)
project(ConanTest)

find_package(fmt REQUIRED)

add_executable(ConanTest main.cpp)
target_link_libraries(ConanTest fmt::fmt)
