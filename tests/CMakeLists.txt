#-----------------------------------------------------------------------------------------------------------------------
# Google Test
#-----------------------------------------------------------------------------------------------------------------------
include(GoogleTest)
enable_testing()

#-----------------------------------------------------------------------------------------------------------------------
# Target: cpp_algorithms_test
# Alias: cpp_algorithms::cpp_algorithms_test
# Type: Executable
# Dependencies: GTest::gtest_main, GTest::gmock_main, cpp_algorithms::cpp_algorithms_headers
#-----------------------------------------------------------------------------------------------------------------------
# Target definition
add_executable(cpp_algorithms_test)

# Target alias
add_executable(cpp_algorithms::cpp_algorithms_test ALIAS cpp_algorithms_test)

# Target sources
target_sources(cpp_algorithms_test
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/cpp_algorithms_test.cpp
)

# Target dependencies
target_link_libraries(cpp_algorithms_test
    PRIVATE
        cpp_algorithms::cpp_algorithms_headers
        GTest::gtest_main
        GTest::gmock_main
)

# Test discovery
gtest_discover_tests(cpp_algorithms_test)