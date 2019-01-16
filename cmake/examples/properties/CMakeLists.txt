project(properties)

####################
#  propsgs-server
####################
ADD_CUSTOM_COMMAND(
	OUTPUT ${CMAKE_CURRENT_BINARY_DIR}/propsgs-glue-adaptor.h
	COMMAND ${CMAKE_CURRENT_BINARY_DIR}/bin/dbusxx-xml2cpp ${CMAKE_CURRENT_SOURCE_DIR}/../examples/properties/propsgs-introspect.xml --adaptor=${CMAKE_CURRENT_BINARY_DIR}/propsgs-glue-adaptor.h --
	DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/../examples/properties/propsgs-introspect.xml
)

add_executable(propsgs-server
	${CMAKE_CURRENT_BINARY_DIR}/propsgs-glue-adaptor.h
	${CMAKE_CURRENT_SOURCE_DIR}/../examples/properties/propsgs-server.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/../examples/properties/propsgs-server.h
)
target_link_libraries(propsgs-server dbus-c++-1 ${DBUS_LIBS})



####################
#  propsgs-client
####################
ADD_CUSTOM_COMMAND(
	OUTPUT ${CMAKE_CURRENT_BINARY_DIR}/propsgs-glue-proxy.h
	COMMAND ${CMAKE_CURRENT_BINARY_DIR}/bin/dbusxx-xml2cpp ${CMAKE_CURRENT_SOURCE_DIR}/../examples/properties/propsgs-introspect.xml --proxy=${CMAKE_CURRENT_BINARY_DIR}/propsgs-glue-proxy.h --
	DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/../examples/properties/propsgs-introspect.xml
)

#add_executable(propsgs-client
#	${CMAKE_CURRENT_BINARY_DIR}/propsgs-glue-proxy.h
#	${CMAKE_CURRENT_SOURCE_DIR}/../examples/properties/propsgs-client.cpp
#	${CMAKE_CURRENT_SOURCE_DIR}/../examples/properties/propsgs-client.h
#
#)
#target_link_libraries(propsgs-client dbus-c++-1 ${DBUS_LIBS} ${LIBEXPAT_LIBRARIES})
