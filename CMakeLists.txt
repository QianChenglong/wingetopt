
PROJECT(wingetopt)

cmake_minimum_required(VERSION 2.8)

list(APPEND inc_dir
	"${CMAKE_CURRENT_SOURCE_DIR}/src")

add_library(wingetopt STATIC src/getopt.c src/getopt.h)

list(APPEND definitions
	_CRT_SECURE_NO_WARNINGS)

set_target_properties(wingetopt PROPERTIES
	COMPILE_DEFINITIONS ${definitions}
	INCLUDE_DIRECTORIES ${inc_dir}
	INTERFACE_INCLUDE_DIRECTORIES ${inc_dir}
	)

install(FILES src/getopt.h DESTINATION include)
install(TARGETS wingetopt LIBRARY DESTINATION lib ARCHIVE DESTINATION lib)
