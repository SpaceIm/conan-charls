cmake_minimum_required(VERSION 3.1.3)
project(test_package)

set(CMAKE_VERBOSE_MAKEFILE TRUE)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

add_executable(test_package_c test_package.c)
target_link_libraries(test_package_c ${CONAN_LIBS})

add_executable(test_package_cpp test_package.cpp)
target_link_libraries(test_package_cpp ${CONAN_LIBS})
set_property(TARGET test_package_cpp PROPERTY CXX_STANDARD 14)
