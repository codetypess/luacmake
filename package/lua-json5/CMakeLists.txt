cmake_minimum_required(VERSION 3.20)

set(CMAKE_CXX_VISIBILITY_PRESET hidden)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_subdirectory(${LUACMAKE_SOURCE_DIR}/jsoncpp jsoncpp)

olua_add_library(json5
  ${LUACMAKE_SOURCE_DIR}/src/lua_json5.h
  ${LUACMAKE_SOURCE_DIR}/src/lua_json5.cpp
  ${LUACMAKE_SOURCE_DIR}/src/json5_lua.h
  ${LUACMAKE_SOURCE_DIR}/olua/olua.h
  ${LUACMAKE_SOURCE_DIR}/olua/olua.hpp
  ${LUACMAKE_SOURCE_DIR}/olua/olua.c
  ${LUACMAKE_SOURCE_DIR}/jsoncpp/src/lib_json/json_tool.h
  ${LUACMAKE_SOURCE_DIR}/jsoncpp/src/lib_json/json_reader.cpp
  ${LUACMAKE_SOURCE_DIR}/jsoncpp/src/lib_json/json_valueiterator.inl
  ${LUACMAKE_SOURCE_DIR}/jsoncpp/src/lib_json/json_value.cpp
  ${LUACMAKE_SOURCE_DIR}/jsoncpp/src/lib_json/json_writer.cpp

  INCLUDE_DIRS
    ${LUACMAKE_SOURCE_DIR}/json5cpp
    ${LUACMAKE_SOURCE_DIR}/olua
    ${LUACMAKE_SOURCE_DIR}/jsoncpp/include
)
