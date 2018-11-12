cmake_minimum_required(VERSION 3.2)
project(i3wm_ipc)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(extern)
add_subdirectory(extern/i3ipcpp)

add_executable(i3wm_ipc src/main.cpp)

# target_link_libraries(  ${EXTERN_LIBRARIES} ${Vulkan_LIBRARIES})

add_custom_command(TARGET i3wm_ipc POST_BUILD
  COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_CURRENT_BINARY_DIR}/compile_commands.json ${CMAKE_CURRENT_SOURCE_DIR})

