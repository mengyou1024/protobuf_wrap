cmake_minimum_required(VERSION 3.10)

add_compile_options(
    -finput-charset=UTF-8 # 源文件字符集
    -fexec-charset=GBK # 可执行文件字符集
)

project(example)

add_subdirectory(.. protobuf)

add_executable(${PROJECT_NAME} main.cpp Person.pb.cc)

target_include_directories(${PROJECT_NAME} PUBLIC "include")

target_link_libraries(${PROJECT_NAME} PRIVATE protobuf::libprotobuf)
