cmake_minimum_required(VERSION 3.1)
project(sqlite)

set(SQLITE_SOURCE_FILES
    sqlite3.c
    sqlite3.h
    Assertion.h
	Column.h
	Database.h
	Exception.h
	SQLiteCpp.h
	Statement.h
	Transaction.h
	Column.cpp
	Database.cpp
	Statement.cpp
	Transaction.cpp)

add_library(sqlite ${SQLITE_SOURCE_FILES})

target_include_directories(sqlite PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
