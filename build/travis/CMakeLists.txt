cmake_minimum_required(VERSION 3.1 FATAL_ERROR)

project(demo LANGUAGES CXX)

find_package(SPL REQUIRED)

if (UNIX)
	set(MATH_LIBRARY "m")
else()
	set(MATH_LIBRARY "")
endif()

message("SPL_FOUND ${SPL_FOUND}")
message("SPL_INCLUDE_DIRS ${SPL_INCLUDE_DIRS}")
message("SPL_LIBRARY_DIRS ${SPL_LIBRARY_DIRS}")
message("SPL_LIBRARIES ${SPL_LIBRARIES}")

include_directories(${SPL_INCLUDE_DIRS})
link_directories(${SPL_LIBRARY_DIRS})
link_libraries(${SPL_LIBRARIES} ${MATH_LIBRARY})

add_executable(filterDesignDemo filterDesignDemo.cpp)
