project(wingetopt)

cmake_minimum_required(VERSION 2.8)

list(APPEND inc_dir
	"${CMAKE_CURRENT_SOURCE_DIR}/src")

list(APPEND srcs
	"src/getopt.c")

list(APPEND hdrs
	"src/getopt.h")

list(APPEND definitions
	"_CRT_SECURE_NO_WARNINGS")

add_library(wingetopt STATIC "${srcs}" "${hdrs}")

set_target_properties(wingetopt PROPERTIES
	PUBLIC_HEADER "${hdrs}"
	COMPILE_DEFINITIONS "${definitions}"
	INCLUDE_DIRECTORIES "${inc_dir}"
	INTERFACE_INCLUDE_DIRECTORIES "${inc_dir}"
	)

install(TARGETS wingetopt
	LIBRARY DESTINATION lib COMPONENT lib
	ARCHIVE DESTINATION lib COMPONENT lib
	RUNTIME DESTINATION bin COMPONENT bin
	PUBLIC_HEADER DESTINATION include COMPONENT dev)
