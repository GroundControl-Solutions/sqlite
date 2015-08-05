cmake_minimum_required(VERSION 3.1)
project(sqlite)

set(SQLITE_SOURCE_FILES
    sqlite3.c
    sqlite3.h)

add_library(sqlite ${SQLITE_SOURCE_FILES})
