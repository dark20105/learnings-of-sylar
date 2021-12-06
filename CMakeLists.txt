cmake_minimum_required(VERSION 3.0)
project(sylar)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

# 显示详细的原始编译信息，主要用于定位一些链接错误，看看库路径什么的是否配置对
set(CMAKE_VERBOSE_MAKEFILE ON)

# 编译选项
option(BUILD_TEST "ON for compile test" OFF)
option(BUILD_LIBS "ON for compile libs" OFF)
option(BUILD_STATIC_LIB "ON for compiler static lib" OFF)
option(BUILD_SHARED_LIBS "OFF for compile static lib" ON)

set(CMAKE_CXX_FLAGS "-std=c++11 -Wall")
set(CMAKE_C_FLAGS "-std=c11")

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/bin)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

set(COMPONENT_DIR ${CMAKE_SOURCE_DIR}/component)
set(PLUGIN_DIR ${CMAKE_SOURCE_DIR}/plugin)

link_libraries( pthread stdc++)

include_directories(${COMPONENT_DIR})
include_directories(${PLUGIN_DIR})
include_directories(${CMAKE_SOURCE_DIR}/inc)

# find_package(Boost REQUIRED)
# if(Boost_FOUND)
#     include_directories(${Boost_INCLUDE_DIRS})
# endif()

# find_package(MySQL REQUIRED)
# if(MYSQL_FOUND)
#     include_directories(${MYSQL_INCLUDE_DIR})
# endif()

# find_package(Protobuf)
# if(Protobuf_FOUND)
#     include_directories(${Protobuf_INCLUDE_DIRS})
# endif()
# find_package(OpenSSL REQUIRED)
# if(OPENSSL_FOUND)
#     include_directories(${OPENSSL_INCLUDE_DIR})
# endif()

# find_package(ZLIB REQUIRED)
# if(ZLIB_FOUND)
#     include_directories(${ZLIB_INCLUDE_DIR})
# endif()

if(BUILD_LIBS)
add_subdirectory(${COMPONENT_DIR})
    add_subdirectory(${PLUGIN_DIR})
endif()

if(BUILD_TEST)
    add_subdirectory(tests) 
endif()
