cmake_minimum_required (VERSION 3.5)
project (sound CXX)

file(GLOB HEADERS "*.h")
file(GLOB SRC "*.cpp")

find_package(OpenAL REQUIRED)

add_library(sound ${HEADERS} ${SRC})
target_compile_definitions(sound PRIVATE "-DAL_LIBTYPE_STATIC")
target_include_directories(sound PRIVATE "${OPENAL_INCLUDE_DIR}")
target_link_libraries(sound Qt5::Core ${OPENAL_LIBRARY})
