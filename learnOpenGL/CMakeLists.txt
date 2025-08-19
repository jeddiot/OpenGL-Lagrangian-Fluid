cmake_minimum_required(VERSION 3.15)
project(LearnOpenGL)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Include dependencies
include_directories(
    ${CMAKE_SOURCE_DIR}/dependencies/include   # glad, stb, GLFW headers
    ${CMAKE_SOURCE_DIR}/src                    # for glad.c
)

# Gather source files
file(GLOB_RECURSE SOURCES
    "${CMAKE_SOURCE_DIR}/src/*.cpp"
    "${CMAKE_SOURCE_DIR}/src/*.c"
)

# Link directories for precompiled libraries
link_directories(${CMAKE_SOURCE_DIR}/dependencies/lib)

# Create executable
add_executable(${PROJECT_NAME} ${SOURCES})

# Link libraries
target_link_libraries(${PROJECT_NAME} PRIVATE glfw3 opengl32)
