cmake_minimum_required(VERSION 3.20)
project(MarketMicrostructureSimulator)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

if(MSVC)
    # MSVC (Windows)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /W4")
    set(CMAKE_CXX_FLAGS_RELEASE "/O2 /NDEBUG")
    set(CMAKE_CXX_FLAGS_DEBUG "/Z7 /Od")
else()
    # GCC/Clang (Linux/macOS)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Wpedantic")
    set(CMAKE_CXX_FLAGS_RELEASE "-O3 -DNDEBUG")
    set(CMAKE_CXX_FLAGS_DEBUG "-g -O0")
endif()

add_subdirectory(cpp)

enable_testing()