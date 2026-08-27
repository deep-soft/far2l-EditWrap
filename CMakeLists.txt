project(EditWrap)

set(SOURCES
src/EditWrap.cpp 
)

add_library (EditWrap MODULE ${SOURCES})

target_link_libraries(EditWrap utils far2l)

target_compile_definitions(EditWrap PRIVATE -DWINPORT_DIRECT -DUNICODE -DFAR_DONT_USE_INTERNALS)

target_include_directories(EditWrap PRIVATE .)
target_include_directories(EditWrap PRIVATE ${CMAKE_SOURCE_DIR}/WinPort)
target_include_directories(EditWrap PRIVATE ${CMAKE_SOURCE_DIR}/far2l/far2sdk)

set_target_properties(EditWrap
    PROPERTIES
        LIBRARY_OUTPUT_DIRECTORY "${INSTALL_DIR}/Plugins/EditWrap/plug"
        PREFIX ""
        SUFFIX ".far-plug-wide")
