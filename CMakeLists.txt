cmake_minimum_required(VERSION 3.11)
project(sqlite)

set(SQLITE3_TARBALL_DIR "sqlite-amalgamation-3260000")
set(SQLITECPP_TARBALL_DIR "SQLiteCpp-2.2.0")

file(GLOB SQLITECPP_HEADERS ${SQLITECPP_TARBALL_DIR}/include/SQLiteCpp/*.h)
file(GLOB SQLITECPP_SOURCES ${SQLITECPP_TARBALL_DIR}/src/*.cpp)

set(SQLITE_SOURCE_FILES
	${SQLITE3_TARBALL_DIR}/sqlite3.h
	${SQLITE3_TARBALL_DIR}/sqlite3.c
	${SQLITECPP_SOURCES}
)

add_library(sqlite ${SQLITE_SOURCE_FILES})

target_include_directories(sqlite
	PUBLIC
	${CMAKE_CURRENT_SOURCE_DIR}/${SQLITE3_TARBALL_DIR}
	${CMAKE_CURRENT_SOURCE_DIR}/${SQLITECPP_TARBALL_DIR}/include
)
