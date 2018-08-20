cmake_minimum_required(VERSION 2.9)
project(libhttp)

if(MSVC)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Ox -Ot -GT -volatile:iso -J -sdl -Wall -wd4464 -wd4710 -wd4711 -wd4201 -wd4820")
else()
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wextra -Wstrict-prototypes -Wshadow -Wpointer-arith -Wformat-security -Winit-self -Wcast-qual -Wcast-align -Wwrite-strings -Wnested-externs -Wredundant-decls -Werror -O3 -funsigned-char")
endif(MSVC)

include_directories(include)
add_definitions(-DUSE_STACK_SIZE=102400)

add_subdirectory(src)
