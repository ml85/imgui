cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

set(PROJECT_NAME imgui)

project(${PROJECT_NAME})

set(LIBRARY_NAME imgui)

set(CMAKE_CXX_FLAGS "-g -Wall")

set(SOURCE_FILES
        include/imgui/imgui.h
        src/imconfig.h
        src/imgui.cpp
        src/imgui_demo.cpp
        src/imgui_draw.cpp
        src/imgui_internal.h
        src/stb_rect_pack.h
        src/stb_textedit.h
        src/stb_truetype.h
)

include_directories(include/imgui src)

add_library(imgui ${SOURCE_FILES})

target_include_directories(${LIBRARY_NAME} PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)
