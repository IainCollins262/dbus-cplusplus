project(libdbus-c++)

set (DBUS_SOURCE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../src")

add_library(dbus-c++-1 SHARED
	${DBUS_SOURCE_PATH}/connection.cpp
	${DBUS_SOURCE_PATH}/debug.cpp
	${DBUS_SOURCE_PATH}/dispatcher.cpp
	${DBUS_SOURCE_PATH}/error.cpp
	${DBUS_SOURCE_PATH}/eventloop-integration.cpp
	${DBUS_SOURCE_PATH}/eventloop.cpp
	${DBUS_SOURCE_PATH}/interface.cpp
	${DBUS_SOURCE_PATH}/introspection.cpp
	${DBUS_SOURCE_PATH}/message.cpp
	${DBUS_SOURCE_PATH}/object.cpp
	${DBUS_SOURCE_PATH}/pendingcall.cpp
	${DBUS_SOURCE_PATH}/pipe.cpp
	${DBUS_SOURCE_PATH}/property.cpp
	${DBUS_SOURCE_PATH}/server.cpp
	${DBUS_SOURCE_PATH}/types.cpp
	${DBUS_SOURCE_PATH}/connection_p.h
	${DBUS_SOURCE_PATH}/dispatcher_p.h
	${DBUS_SOURCE_PATH}/internalerror.h
	${DBUS_SOURCE_PATH}/message_p.h
	${DBUS_SOURCE_PATH}/pendingcall_p.h
	${DBUS_SOURCE_PATH}/server_p.h
)

target_link_libraries(dbus-c++-1
	${DBUS_LIBS}
	${PTHREAD_LIBS}
)

install_targets(/lib dbus-c++-1 )

