project(tools)

####################
#  dbusxx-introspect
####################
add_executable(dbusxx-introspect
	${CMAKE_SOURCE_DIR}/../tools/introspect.h
	${CMAKE_SOURCE_DIR}/../tools/introspect.cpp
)
target_link_libraries(dbusxx-introspect dbus-c++-1 ${DBUS_LIBS})
install_targets(/bin dbusxx-introspect)


####################
#  dbusxx-xml2cpp
####################
add_executable(dbusxx-xml2cpp
	${CMAKE_SOURCE_DIR}/../tools/xml.h
	${CMAKE_SOURCE_DIR}/../tools/xml.cpp
	${CMAKE_SOURCE_DIR}/../tools/xml2cpp.h
	${CMAKE_SOURCE_DIR}/../tools/xml2cpp.cpp
	${CMAKE_SOURCE_DIR}/../tools/generate_adaptor.cpp
	${CMAKE_SOURCE_DIR}/../tools/generate_adaptor.h
	${CMAKE_SOURCE_DIR}/../tools/generate_proxy.cpp
	${CMAKE_SOURCE_DIR}/../tools/generate_proxy.h
	${CMAKE_SOURCE_DIR}/../tools/generator_utils.cpp
	${CMAKE_SOURCE_DIR}/../tools/generator_utils.h
)
target_link_libraries(dbusxx-xml2cpp dbus-c++-1  ${DBUS_LIBS} ${LIBEXPAT_LIBRARIES})
install_targets(/bin dbusxx-xml2cpp)
