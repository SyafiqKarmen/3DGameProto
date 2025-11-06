cmake_minimum_required(VERSION 3.10)
project(ArmorSimulation)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Use optimization flags for MinGW
if(MINGW)
    add_compile_options(-O3 -march=native -flto)
endif()

# SDL3 paths
set(SDL3_DIR "${CMAKE_SOURCE_DIR}/external/SDL3-3.2.26")

include_directories(${SDL3_DIR}/include)
link_directories(${SDL3_DIR}/lib)

# Your main executable
add_executable(ArmorSimulation src/Main.cpp)

# Link SDL3
target_link_libraries(ArmorSimulation SDL3)
