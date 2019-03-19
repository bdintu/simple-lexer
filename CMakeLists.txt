cmake_minimum_required(VERSION 3.5)
project (SimpleLexer)

find_package(FLEX)

FLEX_TARGET(Parser src/simple.flex ${CMAKE_CURRENT_BINARY_DIR}/lex.yy.c)

include_directories(${CMAKE_CURRENT_BINARY_DIR})
add_executable(simple ${FLEX_Parser_OUTPUTS})
target_link_libraries(simple ${FLEX_LIBRARIES})
