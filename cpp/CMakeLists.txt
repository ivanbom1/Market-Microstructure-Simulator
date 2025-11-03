set(SIMULATOR_SOURCES
    src/main.cpp
    src/order_book.cpp
    src/simulator.cpp
    src/metrics.cpp
)

set(SIMULATOR_HEADERS
    include/order_book.h
    include/simulator.h
    include/strategies.h
    include/metrics.h
)

add_executable(simulator ${SIMULATOR_SOURCES} ${SIMULATOR_HEADERS})

target_include_directories(simulator PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

if(MSVC)
    target_compile_options(simulator PRIVATE /W4 /WX)
else()
    target_compile_options(simulator PRIVATE -Wall -Wextra -Wpedantic -Werror)
endif()

# add_subdirectory(tests)