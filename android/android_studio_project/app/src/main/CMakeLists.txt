cmake_minimum_required(VERSION 3.22)
project(xenia_android)

add_subdirectory(app/src/main/cpp)

add_library(
    native-lib
    SHARED
    native-lib.cpp
    # Add Xenia source files here as needed
)

# Include directories for Xenia
include_directories(${CMAKE_SOURCE_DIR}/../../../external/xenia/src)

find_library(log-lib log)
target_link_libraries(native-lib ${log-lib})
