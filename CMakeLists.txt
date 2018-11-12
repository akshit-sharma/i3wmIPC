cmake_minimum_required(VERSION 3.2)
project(i3wmIPC)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(extern/i3ipcpp)

include_directories(${I3IPCpp_INCLUDE_DIRS})

add_executable(i3wmIPC src/main.cpp)

target_link_libraries(i3wmIPC ${I3IPCpp_LIBRARIES})

add_custom_command(TARGET i3wmIPC POST_BUILD
  COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_CURRENT_BINARY_DIR}/compile_commands.json ${CMAKE_CURRENT_SOURCE_DIR})

