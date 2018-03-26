#-------------------- cppwebserver -----------------------------------
cmake_minimum_required(VERSION 2.8)

project (ControlAny)

set(CMAKE_BUILD_TYPE Release)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++0x -fpermissive -Wpmf-conversions")
include_directories(include /usr/include/ )


file(GLOB SOURCES 	"${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")

add_executable(cppwebserver ${SOURCES})
target_link_libraries(cppwebserver pthread cpprest ssl crypto boost_system)

#Installation
#install(TARGETS cppwebserver DESTINATION /usr/sbin/)