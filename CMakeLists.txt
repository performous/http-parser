cmake_minimum_required(VERSION 3.4)
project(http_parser C)

if(CMAKE_BUILD_TYPE MATCHES "Release")
  add_definitions(-DHTTP_PARSER_STRICT=0)
endif()

add_library(http_parser STATIC http_parser.c)

target_include_directories(http_parser INTERFACE ${CMAKE_CURRENT_LIST_DIR})

#install(
#	TARGETS http_parser
#	EXPORT NODEJS_HTTP_PARSER_ALL_TARGETS
#	LIBRARY DESTINATION lib
#	ARCHIVE DESTINATION lib
#	RUNTIME DESTINATION bin
#)

#install(
#	EXPORT NODEJS_HTTP_PARSER_ALL_TARGETS
#	NAMESPACE unofficial::http_parser::
#	FILE unofficial-http_parser-config.cmake
#	DESTINATION share/unofficial-http_parser
#)

#install(FILES http_parser.h DESTINATION include)
