project(debug_assert_test_package)
cmake_minimum_required(VERSION 2.8)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

add_executable(example example.cpp)
if(NOT MSVC)
    target_compile_options(example PRIVATE -std=c++11)
endif()

target_link_libraries(example PRIVATE ${CONAN_TARGETS})
