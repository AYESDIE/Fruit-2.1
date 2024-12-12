cmake_minimum_required(VERSION 3.10)

project(fruit_project LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pipe -fno-exceptions -fno-rtti -O3 -fstrict-aliasing -fomit-frame-pointer")

set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -lm -s")

set(SOURCES
    src/attack.cpp
    src/board.cpp
    src/book.cpp
    src/eval.cpp
    src/fen.cpp
    src/hash.cpp
    src/list.cpp
    src/main.cpp
    src/material.cpp
    src/move.cpp
    src/move_check.cpp
    src/move_do.cpp
    src/move_evasion.cpp
    src/move_gen.cpp
    src/move_legal.cpp
    src/option.cpp
    src/pawn.cpp
    src/piece.cpp
    src/posix.cpp
    src/protocol.cpp
    src/pst.cpp
    src/pv.cpp
    src/random.cpp
    src/recog.cpp
    src/search.cpp
    src/search_full.cpp
    src/see.cpp
    src/sort.cpp
    src/square.cpp
    src/trans.cpp
    src/util.cpp
    src/value.cpp
    src/vector.cpp
)

add_executable(fruit ${SOURCES})

add_custom_target(custom_clean
    COMMAND ${CMAKE_COMMAND} -E remove_directory ${CMAKE_BINARY_DIR}/CMakeFiles
    COMMAND ${CMAKE_COMMAND} -E remove ${CMAKE_BINARY_DIR}/fruit
    COMMAND ${CMAKE_COMMAND} -E remove ${CMAKE_BINARY_DIR}/CMakeCache.txt
)
