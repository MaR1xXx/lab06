cmake_minimum_required(VERSION 3.4)
project(lab06)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/solver_application)

include(CPack.cmake)
