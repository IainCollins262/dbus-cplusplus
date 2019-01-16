project(libdbus-c++)

add_library(dbus-c++-1 SHARED
	${CMAKE_SOURCE_DIR}/../src/connection.cpp
	${CMAKE_SOURCE_DIR}/../src/debug.cpp
	${CMAKE_SOURCE_DIR}/../src/dispatcher.cpp
	${CMAKE_SOURCE_DIR}/../src/error.cpp
	${CMAKE_SOURCE_DIR}/../src/eventloop-integration.cpp
	${CMAKE_SOURCE_DIR}/../src/eventloop.cpp
	${CMAKE_SOURCE_DIR}/../src/interface.cpp
	${CMAKE_SOURCE_DIR}/../src/introspection.cpp
	${CMAKE_SOURCE_DIR}/../src/message.cpp
	${CMAKE_SOURCE_DIR}/../src/object.cpp
	${CMAKE_SOURCE_DIR}/../src/pendingcall.cpp
	${CMAKE_SOURCE_DIR}/../src/pipe.cpp
	${CMAKE_SOURCE_DIR}/../src/property.cpp
	${CMAKE_SOURCE_DIR}/../src/server.cpp
	${CMAKE_SOURCE_DIR}/../src/types.cpp
	${CMAKE_SOURCE_DIR}/../src/connection_p.h
	${CMAKE_SOURCE_DIR}/../src/dispatcher_p.h
	${CMAKE_SOURCE_DIR}/../src/internalerror.h
	${CMAKE_SOURCE_DIR}/../src/message_p.h
	${CMAKE_SOURCE_DIR}/../src/pendingcall_p.h
	${CMAKE_SOURCE_DIR}/../src/server_p.h
)

target_link_libraries(dbus-c++-1
	${DBUS_LIBS}
	${PTHREAD_LIBS}
)

install_targets(/lib dbus-c++-1 )

