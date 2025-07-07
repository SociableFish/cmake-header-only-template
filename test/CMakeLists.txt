cmake_minimum_required(VERSION 3.14)
project(test)

include(FetchContent)
FetchContent_Declare(
    googletest
    URL https://github.com/google/googletest/archive/03597a01ee50ed33e9dfd640b249b4be3799d395.zip
)
# For Windows: Prevent overriding the parent project's compiler/linker settings
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)
enable_testing()

add_executable(
    yourlib-test
    # Add more test files here
    test.cpp
)

target_include_directories(yourlib-test PRIVATE ../include)

include(GoogleTest)
gtest_discover_tests(yourlib-test)
target_link_libraries(yourlib-test PRIVATE gtest_main)