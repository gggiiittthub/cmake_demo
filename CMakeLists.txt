CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(demo_proj)

SET(CMAKE_VERBOSE_MAKEFILE ON)

SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall")
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")
SET(CMAKE_C_FLAGS_DEBUG "-g -O0")
SET(CMAKE_CXX_FLAGS_DEBUG "-g -O0")
SET(CMAKE_C_FLAGS_RELEASE "-g -O2")
SET(CMAKE_CXX_FLAGS_RELEASE "-g -O2")

STRING(FIND "${CMAKE_C_FLAGS} ${CMAKE_CXX_FLAGS}" "-m32" FOUND_IDX)
IF(NOT FOUND_IDX EQUAL -1)
    SET(USE_32BIT TRUE)
ELSE()
    SET(USE_32BIT FALSE)
ENDIF()

ENABLE_TESTING()

ADD_SUBDIRECTORY(extlib)
ADD_SUBDIRECTORY(public)
ADD_SUBDIRECTORY(proto)
ADD_SUBDIRECTORY(module_xxx)
ADD_SUBDIRECTORY(module_yyy)
ADD_SUBDIRECTORY(module_mock)
