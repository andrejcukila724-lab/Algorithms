cmake_minimum_required(VERSION 3.5)

project(Lab1)

set(CMAKE_CXX_STANDARD 20)

include_directories(include)

add_executable(grad src/grad.cpp)
add_executable(nab src/nab.cpp)
add_executable(test_array tests/test_array.cpp)

enable_testing()
add_test(
        NAME grad_test1
        COMMAND grad ${CMAKE_SOURCE_DIR}/tests/test_grad1.txt
)
set_tests_properties(
        grad_test1
        PROPERTIES
        PASS_REGULAR_EXPRESSION "4 3 2 1"
)
add_test(
        NAME grad_test2
        COMMAND grad ${CMAKE_SOURCE_DIR}/tests/test_grad2.txt
)
set_tests_properties(
        grad_test2
        PROPERTIES
        PASS_REGULAR_EXPRESSION "1 1 0 4"
)
add_test(
        NAME grad_test3
        COMMAND grad ${CMAKE_SOURCE_DIR}/tests/test_grad3.txt
)
set_tests_properties(
        grad_test3
        PROPERTIES
        PASS_REGULAR_EXPRESSION "9 0 0 0"
)
add_test(
        NAME nab_test1
        COMMAND nab ${CMAKE_SOURCE_DIR}/tests/test_nab1.txt
)
set_tests_properties(
        nab_test1
        PROPERTIES
        PASS_REGULAR_EXPRESSION "Самое частое число: 987 \\(встречается 5 раз\\)"

)
add_test(
        NAME nab_test2
        COMMAND nab ${CMAKE_SOURCE_DIR}/tests/test_nab2.txt
)
set_tests_properties(
        nab_test2
        PROPERTIES
        PASS_REGULAR_EXPRESSION "Самое частое число: 666 \\(встречается 2 раз\\)"

)
add_test(
        NAME nab_test3
        COMMAND nab ${CMAKE_SOURCE_DIR}/tests/test_nab3.txt
)
set_tests_properties(
        nab_test3
        PROPERTIES
        PASS_REGULAR_EXPRESSION "Самое частое число: 950 \\(встречается 9 раз\\)"

)
add_test(
        NAME Array_test
        COMMAND test_array
)
set_tests_properties(
        Array_test
        PROPERTIES
        PASS_REGULAR_EXPRESSION "Size: 5.*Array: 10 20 30 40 50.*Original: 10.*Copy: 999.*Self-assignment: 10 20 30 40 50.*Error: Index out of range"

)