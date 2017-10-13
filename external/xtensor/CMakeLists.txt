cmake_minimum_required(VERSION 2.8.8)
project(xtensor_builder CXX)
include(ExternalProject)
find_package(Git REQUIRED)

ExternalProject_Add(
    xtensor
    PREFIX ${CMAKE_BINARY_DIR}/xtensor
    GIT_REPOSITORY https://github.com/QuantStack/xtensor.git
    TIMEOUT 10
    UPDATE_COMMAND ${GIT_EXECUTABLE} pull
    CONFIGURE_COMMAND ""
    BUILD_COMMAND ""
    INSTALL_COMMAND ""
    LOG_DOWNLOAD ON
)

ExternalProject_Get_Property(xtensor source_dir)
set(XTENSOR_MODULE_PATH "${source_dir}" PARENT_SCOPE)
set(XTENSOR_INCLUDE_PATH ${source_dir}/include PARENT_SCOPE)
