cmake_minimum_required(VERSION 2.6)
set(CMAKE_BUILD_TYPE Debug)
enable_testing()
add_executable (server server.c)
add_executable (client client.c)
add_library(socket_utils SHARED socket_utils.c)
add_library(communication_utils SHARED communication_utils.c)
add_library(stack SHARED stack.c)
add_library(box_utils SHARED box_utils.c)


target_link_libraries(client LINK_PUBLIC pthread)
target_link_libraries(server LINK_PUBLIC socket_utils)
target_link_libraries(client LINK_PUBLIC socket_utils)
target_link_libraries(server LINK_PUBLIC communication_utils)
target_link_libraries(client LINK_PUBLIC communication_utils)
target_link_libraries(server LINK_PUBLIC stack)
target_link_libraries(client LINK_PUBLIC stack)
target_link_libraries(server LINK_PUBLIC box_utils)
target_link_libraries(client LINK_PUBLIC box_utils)
