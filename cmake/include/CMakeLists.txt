project(dbus-c++-inc)

install_files(/include/dbus-1.0/dbus-c++ FILES
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/api.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/connection.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/dbus.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/debug.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/dispatcher.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/error.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/eventloop-integration.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/eventloop.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/interface.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/introspection.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/message.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/object.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/pendingcall.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/property.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/refptr_impl.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/server.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/types.h
	${CMAKE_SOURCE_DIR}/../include/dbus-c++/util.h
)
