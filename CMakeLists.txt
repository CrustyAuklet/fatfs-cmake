cmake_minimum_required(VERSION 3.15)
project(FatFs
        VERSION 2.1.4
        DESCRIPTION "STM32 fork of FatFs library"
        LANGUAGES C ASM)

include_guard(GLOBAL)

add_library(FatFS INTERFACE)
add_library(FatFS::FatFS ALIAS FatFS)
target_include_directories(FatFS INTERFACE ${CMAKE_CURRENT_LIST_DIR}/src)

target_sources(FatFS INTERFACE
        ${CMAKE_CURRENT_LIST_DIR}/src/diskio.c
        ${CMAKE_CURRENT_LIST_DIR}/src/diskio.h
        ${CMAKE_CURRENT_LIST_DIR}/src/ff_gen_drv.c
        ${CMAKE_CURRENT_LIST_DIR}/src/ff_gen_drv.h
        ${CMAKE_CURRENT_LIST_DIR}/src/ff.c
        ${CMAKE_CURRENT_LIST_DIR}/src/ff.h
        ${CMAKE_CURRENT_LIST_DIR}/src/integer.h

        ${CMAKE_CURRENT_LIST_DIR}/src/option/syscall.c
        ${CMAKE_CURRENT_LIST_DIR}/src/option/unicode.c
        )
