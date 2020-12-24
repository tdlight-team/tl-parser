cmake_minimum_required(VERSION 3.0)
project(tl-parser)

if (MSVC)
	set(CMAKE_EXE_LINKER_FLAGS "/SUBSYSTEM:CONSOLE")
endif()

add_executable(${PROJECT_NAME} crc32.h crc32.c tlc.c tl-parser.c tl-parser.h tl-parser-tree.h tl-tl.h portable_endian.h wingetopt.c wingetopt.h)
if (NOT WIN32)
	target_link_libraries(${PROJECT_NAME} m)
endif()
