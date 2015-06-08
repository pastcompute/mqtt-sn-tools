cmake_minimum_required(VERSION 2.8.11)   # <-- target_include_directories() needs 2.8.11
project(mqtt-sn-tools C)

set(BINDIR bin)
set(SBINDIR sbin)
set(LIBDIR lib${LIB_SUFFIX})

set(SOURCES mqtt-sn.c mqtt-sn.h)

#set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Os")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -g")

add_executable(mqtt-sn-pub ${SOURCES} mqtt-sn-pub.c)
add_executable(mqtt-sn-sub ${SOURCES} mqtt-sn-sub.c)
add_executable(mqtt-sn-serial-bridge ${SOURCES} mqtt-sn-serial-bridge.c)

install(TARGETS mqtt-sn-pub RUNTIME DESTINATION ${BINDIR} LIBRARY DESTINATION ${LIBDIR})
install(TARGETS mqtt-sn-sub RUNTIME DESTINATION ${BINDIR} LIBRARY DESTINATION ${LIBDIR})
install(TARGETS mqtt-sn-serial-bridge RUNTIME DESTINATION ${BINDIR} LIBRARY DESTINATION ${LIBDIR})

