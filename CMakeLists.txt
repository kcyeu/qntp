find_package(Qt5 REQUIRED
    COMPONENTS
		Network)
#include_directories(${Qt5Core_INCLUDE_DIRS})
include_directories(${Qt5Network_INCLUDE_DIRS})

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)
set(QNTP_SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src/qntp)
include_directories(${QNTP_SOURCE_DIR})

list(APPEND SOURCES
    ${QNTP_SOURCE_DIR}/NtpClient.cpp
    ${QNTP_SOURCE_DIR}/NtpReply.cpp)

list(APPEND HEADERS 
    ${QNTP_SOURCE_DIR}/NtpClient.h
    ${QNTP_SOURCE_DIR}/config.h
    ${QNTP_SOURCE_DIR}/NtpPacket.h
    ${QNTP_SOURCE_DIR}/QNtp.h
    ${QNTP_SOURCE_DIR}/NtpReply.h
    ${QNTP_SOURCE_DIR}/NtpReply_p.h
    ${QNTP_SOURCE_DIR}/NtpTimestamp.h)

add_library(qntp
    ${SOURCES})