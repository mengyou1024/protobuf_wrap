cmake_minimum_required(VERSION 3.10)
cmake_policy(SET CMP0077 NEW)
project(protobuf_warp)

# Options
set(protobuf_INSTALL OFF)
set(protobuf_BUILD_TESTS OFF)
set(protobuf_BUILD_PROTOBUF_BINARIES ON)
set(protobuf_BUILD_PROTOC_BINARIES OFF)
set(protobuf_BUILD_LIBPROTOC OFF)
set(protobuf_BUILD_LIBUPB OFF)
set(protobuf_DISABLE_RTTI OFF)
set(protobuf_ALLOW_CCACHE OFF)

add_subdirectory(protobuf)

target_include_directories(libprotobuf INTERFACE ${protobuf_SOURCE_DIR}/src)
target_include_directories(libprotobuf-lite INTERFACE ${protobuf_SOURCE_DIR}/src)
