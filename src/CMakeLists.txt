set(TARGET game)

aux_source_directory(. SRC_LIST)


SET(SFML_STATIC_LIBRARIES TRUE)

SET(SFML_ROOT "D:/Program Files (x86)/SFML-2.1")

FIND_PACKAGE(SFML 2 COMPONENTS audio graphics window system)

INCLUDE_DIRECTORIES(${SFML_INCLUDE_DIR})
ADD_EXECUTABLE(${TARGET} ${SRC_LIST})
target_link_libraries(${TARGET} ${SFML_LIBRARIES} -Wl,--subsystem=windows -mwindows)

if (SFML_STATIC_LIBRARIES)
    add_definitions(-DSFML_STATIC)
endif ()

INSTALL(TARGETS ${TARGET} DESTINATION .)
