cmake_minimum_required(VERSION 3.5)
PROJECT(xp-xtensor)

set(CMAKE_CXX_STANDARD 14)
set (CMAKE_CXX_STANDARD_REQUIRED ON)

set(EXT_PROJECTS_DIR ${PROJECT_SOURCE_DIR}/external)

add_subdirectory(${EXT_PROJECTS_DIR}/xtl)
add_subdirectory(${EXT_PROJECTS_DIR}/xtensor)

include_directories(${XTL_INCLUDE_PATH})
include_directories(${XTENSOR_INCLUDE_PATH})

set(SOURCES
    source/main.cpp
)

add_executable(${PROJECT_NAME} ${SOURCES})
target_link_libraries(${PROJECT_NAME})
