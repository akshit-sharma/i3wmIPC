cmake_minimum_required(VERSION 3.0)

include(ExternalProject)

find_package(CURL REQUIRED) # curl is required for ExternalProject_Add

ExternalProject_Add(i3ipcpp
  PREFIX ${CMAKE_BINARY_DIR}/i3ipcpp
  SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/i3ipcpp
  INSTALL_DIR ${CMAKE_BINARY_DIR}/i3ipcpp
  
  GIT_REPOSITORY https://github.com/drmgc/i3ipcpp

  CONFIGURE_COMMAND ""
  INSTALL_COMMAND ""
  BUILD_COMMAND ""

  )


