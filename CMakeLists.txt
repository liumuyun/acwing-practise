cmake_minimum_required(VERSION 3.21)
project(acwing_practise)

set(CMAKE_CXX_STANDARD 14)

add_executable(acwing_practise HelloWorld.cpp)

file (GLOB_RECURSE files *.cpp)
foreach (file ${files})
    string(REGEX REPLACE ".+/(.+)\\..*" "\\1" exe ${file})
    add_executable (${exe} ${file})
    message (\ \ \ \ --\ src/${exe}.cpp\ will\ be\ compiled\ to\ bin/${exe})
endforeach ()