cmake_minimum_required(VERSION 2.8.8)
project(xtl_builder CXX)
include(ExternalProject)
find_package(Git REQUIRED)

ExternalProject_Add(
    xtl
    PREFIX ${CMAKE_BINARY_DIR}/xtl
    GIT_REPOSITORY https://github.com/QuantStack/xtl.git
    TIMEOUT 10
    UPDATE_COMMAND ${GIT_EXECUTABLE} pull
    CONFIGURE_COMMAND ""
    BUILD_COMMAND ""
    INSTALL_COMMAND ""
    LOG_DOWNLOAD ON
)

ExternalProject_Get_Property(xtl source_dir)
set(XTL_MODULE_PATH "${source_dir}" PARENT_SCOPE)
set(XTL_INCLUDE_PATH ${source_dir}/include PARENT_SCOPE)
