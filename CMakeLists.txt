PROJECT(rpc)
CMAKE_MINIMUM_REQUIRED (VERSION 3.14)
FIND_PACKAGE(Protobuf REQUIRED)
SET(CMAKE_CXX_FLAGS "-g -Wall -Werror -std=c++11")

ADD_SUBDIRECTORY(proto)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_BINARY_DIR})
include_directories(${Protobuf_INCLUDE_DIRS})
ADD_EXECUTABLE(main main.cpp)
TARGET_LINK_LIBRARIES(main proto ${PROTOBUF_LIBRARY})
