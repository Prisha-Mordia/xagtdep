# CMakeLists.txt
cmake_minimum_required(VERSION 3.14)
project(dagtdep)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_CXX_EXTENSIONS False)

include(FetchContent)

set(MOCKTURTLE_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(MOCKTURTLE_BUILD_TESTS OFF CACHE BOOL "" FORCE)
FetchContent_Declare(
  mockturtle
  GIT_REPOSITORY https://github.com/lsils/mockturtle.git
  GIT_TAG        master
)
FetchContent_MakeAvailable(mockturtle)

set(CATERPILLAR_TEST OFF CACHE BOOL "" FORCE)
set(CATERPILLAR_EXAMPLES OFF CACHE BOOL "" FORCE)
set(CATERPILLAR_EXPERIMENTS OFF CACHE BOOL "" FORCE)
FetchContent_Declare(
  caterpillar
  GIT_REPOSITORY https://github.com/gmeuli/caterpillar.git
  GIT_TAG        master
)
FetchContent_MakeAvailable(caterpillar)

add_subdirectory(src)
add_subdirectory(test)