cmake_minimum_required(VERSION 3.2)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
project(Megamovement LANGUAGES CXX VERSION 1.2)
set(CMAKE_CXX_STANDARD 20) 
set(CMAKE_CXX_STANDARD_REQUIRED True)

#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++20 -Werror -Wall -Wextra -Wpedantic -march=native -g")
#set(CMAKE_CXX_FLAGS_RELEASE "-std=c++20 -O2 -march=native")

set(PROJECT_SOURCES_DIR src)
file(GLOB_RECURSE SOURCES ${PROJECT_SOURCES_DIR}/*.cpp)

include_directories(
  src
  )

#-------------- SDL2 --------------#
find_package(SDL2 REQUIRED)
include_directories(${PROJECT_NAME} ${SDL2_INCLUDE_DIRS})
#-------------- SDL2 --------------#

add_executable(${PROJECT_NAME} ${SOURCES})
target_link_libraries(${PROJECT_NAME} ${SDL2_LIBRARIES})
