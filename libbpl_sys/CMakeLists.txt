cmake_minimum_required(VERSION 3.25)

project(bpl_sys)

set(CMAKE_CXX_STANDARD 20)

option(BUILD_SHARED_LIBS "Build using shared libraries" ON)
include_directories(include)

set(PUBLIC_HEADER include/bpl/sys/Batteries.h include/bpl/sys/Battery.h)
set(SOURCE_FILES src/Battery.cpp src/Batteries.cpp)

add_library(bpl_sys SHARED ${SOURCE_FILES} ${PUBLIC_HEADER} )

install(TARGETS bpl_sys DESTINATION lib)
install(FILES include/bpl/sys/Battery.h DESTINATION include/bpl/sys)
install(FILES include/bpl/sys/Batteries.h DESTINATION include/bpl/sys)
