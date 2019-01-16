project(tools)

set (DBUS_TOOLS_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../tools")

####################
#  dbusxx-introspect
####################
add_executable(dbusxx-introspect
	${DBUS_TOOLS_PATH}/introspect.h
	${DBUS_TOOLS_PATH}/introspect.cpp
)
target_link_libraries(dbusxx-introspect dbus-c++-1 ${DBUS_LIBS})
install_targets(/bin dbusxx-introspect)


####################
#  dbusxx-xml2cpp
####################
add_executable(dbusxx-xml2cpp
	${DBUS_TOOLS_PATH}/xml.h
	${DBUS_TOOLS_PATH}/xml.cpp
	${DBUS_TOOLS_PATH}/xml2cpp.h
	${DBUS_TOOLS_PATH}/xml2cpp.cpp
	${DBUS_TOOLS_PATH}/generate_adaptor.cpp
	${DBUS_TOOLS_PATH}/generate_adaptor.h
	${DBUS_TOOLS_PATH}/generate_proxy.cpp
	${DBUS_TOOLS_PATH}/generate_proxy.h
	${DBUS_TOOLS_PATH}/generator_utils.cpp
	${DBUS_TOOLS_PATH}/generator_utils.h
)
target_link_libraries(dbusxx-xml2cpp dbus-c++-1  ${DBUS_LIBS} ${LIBEXPAT_LIBRARIES})
install_targets(/bin dbusxx-xml2cpp)
