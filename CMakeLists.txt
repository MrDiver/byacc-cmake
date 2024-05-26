cmake_minimum_required(VERSION 3.10)

project(yacc C)

set(CMAKE_C_STANDARD 17)

if(WIN32)
	add_compile_definitions("__WIN32__")
endif()

set(YACC_SOURCES
	"src/closure.c"
	"src/error.c"
	"src/lalr.c"
	"src/lr0.c"
	"src/main.c"
	"src/mkpar.c"
	"src/output.c"
	"src/reader.c"
	"src/skeleton.c"
	"src/symtab.c"
	"src/verbose.c"
	"src/warshall.c"
)

add_executable(${PROJECT_NAME} ${YACC_SOURCES})
target_include_directories(${PROJECT_NAME} PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/src")
