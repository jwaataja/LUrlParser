cmake_minimum_required(VERSION 3.0)

project("LUrlParser")

option(BUILD_EXAMPLE "Build the example" OFF)

add_library(LUrlParser STATIC LUrlParser.cpp)
set_property(TARGET LUrlParser PROPERTY CXX_STANDARD 11)
set_property(TARGET LUrlParser PROPERTY CXX_STANDARD_REQUIRED ON)

target_include_directories(LUrlParser PUBLIC ${PROJECT_SOURCE_DIR})

if(BUILD_EXAMPLE)
	add_executable(Example Example.cpp LUrlParser.cpp LUrlParser.h)
	set_property(TARGET Example PROPERTY CXX_STANDARD 11)
	set_property(TARGET Example PROPERTY CXX_STANDARD_REQUIRED ON)
endif()
