project(dbus-c++)

set (DBUS_CPLUSPLUS_VERSION 0.5.0)
set (DBUS_CPLUSPLUS_VERSION_STRING "${DBUS_CPLUSPLUS_VERSION}")

# we need to be up to date
CMAKE_MINIMUM_REQUIRED(VERSION 2.4.4 FATAL_ERROR)
if(COMMAND cmake_policy)
    cmake_policy(SET CMP0003 NEW)
endif(COMMAND cmake_policy)

# where to look first for cmake modules, before ${CMAKE_ROOT}/Modules/ is checked
set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/modules")

#enable building of shared library
SET(BUILD_SHARED_LIBS ON)

# include local header first to avoid using old installed header
set (CMAKE_INCLUDE_PATH ${CMAKE_INCLUDE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/..)

# search for required packages
find_package(LibExpat)
find_package(Dbus)

find_library(PTHREAD_LIBS
        NAMES pthread
        PATHS /libs
)
message( STATUS "pthread .... ${PTHREAD_LIBS}")


# do config checks
INCLUDE(ConfigureChecks.cmake)

# @TODO: how to remove last dir from ${CMAKE_CURRENT_SOURCE_DIR} ?
SET(DBUS_CPLUSPLUS_SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/..)
set(CMAKE_DEBUG_POSTFIX "d")
SET(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG}  -D_DEBUG")


set (LIBRARY_OUTPUT_PATH  ${CMAKE_CURRENT_BINARY_DIR}/bin)
set (EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_BINARY_DIR}/bin)

include_directories(
	${CMAKE_CURRENT_SOURCE_DIR}/..
	${CMAKE_CURRENT_SOURCE_DIR}/../include
	${CMAKE_CURRENT_BINARY_DIR}
	${CMAKE_INCLUDE_PATH}
	${CMAKE_LIBRARY_PATH}
	${DBUS_INCLUDES}
)

# linker search directories
link_directories(
	${LIBRARY_OUTPUT_PATH}
	${DBUS_LIBS}
	${CMAKE_LIBRARY_PATH}
)

set (EXT ".exe")

# compiler definitions
add_definitions(-DHAVE_CONFIG_H=1)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/config.h.cmake ${CMAKE_CURRENT_BINARY_DIR}/config.h )

########### subdirs ###############

add_subdirectory( include )
add_subdirectory( src )
add_subdirectory( tools )
#add_subdirectory( examples )


GET_FILENAME_COMPONENT(C_COMPILER ${CMAKE_C_COMPILER} NAME)
GET_FILENAME_COMPONENT(CXX_COMPILER ${CMAKE_CXX_COMPILER} NAME)
