project(dbus-c++-inc)

set (DBUS_INC_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../include")

install_files(/include/dbus-1.0/dbus-c++ FILES
	${DBUS_INC_PATH}/dbus-c++/api.h
	${DBUS_INC_PATH}/dbus-c++/connection.h
	${DBUS_INC_PATH}/dbus-c++/dbus.h
	${DBUS_INC_PATH}/dbus-c++/debug.h
	${DBUS_INC_PATH}/dbus-c++/dispatcher.h
	${DBUS_INC_PATH}/dbus-c++/error.h
	${DBUS_INC_PATH}/dbus-c++/eventloop-integration.h
	${DBUS_INC_PATH}/dbus-c++/eventloop.h
	${DBUS_INC_PATH}/dbus-c++/interface.h
	${DBUS_INC_PATH}/dbus-c++/introspection.h
	${DBUS_INC_PATH}/dbus-c++/message.h
	${DBUS_INC_PATH}/dbus-c++/object.h
	${DBUS_INC_PATH}/dbus-c++/pendingcall.h
	${DBUS_INC_PATH}/dbus-c++/property.h
	${DBUS_INC_PATH}/dbus-c++/refptr_impl.h
	${DBUS_INC_PATH}/dbus-c++/server.h
	${DBUS_INC_PATH}/dbus-c++/types.h
	${DBUS_INC_PATH}/dbus-c++/util.h
)
