cmake_minimum_required(VERSION 3.16)

project(redis-server
    VERSION 1.0
    LANGUAGES CXX
)

# C++17 configuration
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Executable
add_executable(redis-server
    src/server.cpp
)

add_executable(redis-client
    src/client.cpp
)

# Compiler warnings
foreach(target redis-server redis-client)
    target_compile_options(${target} PRIVATE
        -Wall
        -Wextra
        -Wpedantic
        -Werror
    )
endforeach()
