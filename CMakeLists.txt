project(SFMLTest)

cmake_minimum_required(VERSION 2.8)

add_subdirectory(src)

FILE(GLOB_RECURSE RES_FILES res/*)

INSTALL(FILES ${RES_FILES} DESTINATION .)
