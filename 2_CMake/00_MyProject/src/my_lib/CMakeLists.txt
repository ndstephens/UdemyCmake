add_library(Library STATIC my_lib.cc)

target_include_directories(Library PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
