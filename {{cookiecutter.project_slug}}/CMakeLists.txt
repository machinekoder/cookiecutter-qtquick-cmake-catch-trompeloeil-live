cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project({{cookiecutter.project_slug}} LANGUAGES CXX)
enable_testing()

add_subdirectory(app)
add_subdirectory(tests)

add_subdirectory(3rdparty/catch)
add_subdirectory(3rdparty/trompeloeil)
