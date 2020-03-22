
cmake_minimum_required(VERSION 2.8.3)
project(bin2pcd)
 
add_compile_options(-std=c++11)
SET(CMAKE_BUILD_TYPE "Release")

find_package(PCL 1.2 REQUIRED)
 
# 加入Boost setting
find_package(Boost COMPONENTS program_options REQUIRED )
include_directories(${Boost_INCLUDE_DIRS})
link_directories(${Boost_LIBRARY_DIRS})
 
include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})
 
add_executable(${PROJECT_NAME} main.cpp)
 
target_link_libraries (${PROJECT_NAME} ${PCL_LIBRARIES} ${Boost_LIBRARIES} stdc++fs) #此处也有修改
