cmake_minimum_required(VERSION 3.5)
project(raygui)

# Used as public API to be included into other projects
set(raygui_public_headers
    raygui.h
    )

# Sources to be compiled
set(raygui_sources
    raygui.c
    )

add_library(raygui ${raygui_sources} ${raygui_public_headers})

target_link_libraries(raygui PUBLIC raylib)

target_include_directories(	raygui
							PUBLIC
							$<INSTALL_INTERFACE:include>
							$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
							)
