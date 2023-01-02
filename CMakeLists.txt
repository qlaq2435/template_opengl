# CMakeLists.txt
cmake_minimum_required(VERSION 3.14)
project(test)

set(CMAKE_CXX_STANDARD 11)

set(source_code)
file(GLOB_RECURSE source_code ./src/*.cpp ./src/*.c)

add_executable(hello ${source_code})

set(TARGET_LIB -lglfw)
target_link_libraries(hello ${glad} ${TARGET_LIB})

