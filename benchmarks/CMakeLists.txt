#-----------------------------------------------------------------------------------------------------------------------
# Target: cpp_algorithms_benchmark
# Alias: cpp_algorithms::cpp_algorithms_benchmark
# Type: Executable
# Dependencies: benchmark::benchmark_main, cpp_algorithms::cpp_algorithms_headers
#-----------------------------------------------------------------------------------------------------------------------
# Target definition
add_executable(cpp_algorithms_benchmark)

# Target alias
add_executable(cpp_algorithms::cpp_algorithms_benchmark ALIAS cpp_algorithms_benchmark)

# Target sources
target_sources(cpp_algorithms_benchmark
        PRIVATE
            ${CMAKE_CURRENT_SOURCE_DIR}/cpp_algorithms_benchmark.cpp
)

# Target dependencies
target_link_libraries(cpp_algorithms_benchmark
        PRIVATE
            cpp_algorithms::cpp_algorithms_headers
            benchmark::benchmark_main
)
