# Change all instances of yourlib and YOURLIB to your library's name
# Found in:
# ./CMakeLists.txt
# ./test/CMakeLists.txt
cmake_minimum_required(VERSION 3.14)
project(
    yourlib
    VERSION 0.1.0
    LANGUAGES CXX
)
add_library(yourlib INTERFACE)
target_compile_features(yourlib INTERFACE cxx_std_17)

target_include_directories(yourlib INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include)

option(YOURLIB_BUILD_TESTS "Build yourlib tests" ON)
if (${YOURLIB_BUILD_TESTS})
    add_subdirectory(test)
    enable_testing()
endif()