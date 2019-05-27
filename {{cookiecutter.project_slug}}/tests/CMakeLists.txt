cmake_minimum_required (VERSION 3.2)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

find_package(Qt5 COMPONENTS Test REQUIRED)

#############################
## unit tests
#############################
set(TEST_SOURCES
    "main.cpp"
    "tst_calculator.cpp"
    )
add_executable(${PROJECT_NAME}_test ${TEST_SOURCES})
target_link_libraries(${PROJECT_NAME}_test Catch Trompeloeil)
target_link_libraries(${PROJECT_NAME}_test Qt5::Test)
target_link_libraries(${PROJECT_NAME}_test ${PROJECT_NAME}_lib)
enable_testing()

add_test(NAME UnitTests COMMAND ${PROJECT_NAME}_test)
