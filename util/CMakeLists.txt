add_executable(telnet-chatd telnet-chatd.c)
target_link_libraries(telnet-chatd
    libtelnet
)
if(WIN32)
    target_link_libraries(telnet-chatd wsock32 ws2_32)
endif()

if (UNIX)
    add_executable(telnet-client telnet-client.c)
    target_link_libraries(telnet-client
        libtelnet
    )
endif ()

add_executable(telnet-test telnet-test.c)
target_link_libraries(telnet-test
    libtelnet
)

add_executable(telnet-proxy telnet-proxy.c)
target_link_libraries(telnet-proxy
    libtelnet)

if(WIN32)
    target_link_libraries(telnet-proxy wsock32 ws2_32)
endif()
