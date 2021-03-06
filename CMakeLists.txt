CMAKE_MINIMUM_REQUIRED(VERSION 2.8.9)

PROJECT(ApgLib C)

FILE(GLOB src "*.c")

SET(SOURCE
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/Stats.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/Operators.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/Parser.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/Vector.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/UdtLib.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/Trace.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/Memory.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/Tools.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/Ast.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgUtilities/Files.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgUtilities/timer.c
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgUtilities/Utilities.c
)

set(HEADERS
   ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib/Apg.h
)

IF(NOT CMAKE_BUILD_TYPE)
  SET(CMAKE_BUILD_TYPE Release)
ENDIF()

SET(CMAKE_C_FLAGS_RELEASE "-O3")

ADD_LIBRARY(ApgLib ${SOURCE})

SET_TARGET_PROPERTIES(ApgLib PROPERTIES LINKER_LANGUAGE C)

TARGET_INCLUDE_DIRECTORIES(ApgLib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/ApgLib)

