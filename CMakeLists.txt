cmake_minimum_required (VERSION 3.10)
project(imgui VERSION 1.88)

set(IMGUI_DIR ${CMAKE_CURRENT_SOURCE_DIR}/)
add_library(imgui STATIC)
set_property(TARGET imgui PROPERTY CXX_STANDARD 17)

target_sources(imgui
                PRIVATE
                    ${IMGUI_DIR}/imgui_demo.cpp
                    ${IMGUI_DIR}/imgui_draw.cpp
                    ${IMGUI_DIR}/imgui_tables.cpp
                    ${IMGUI_DIR}/imgui_widgets.cpp
                    ${IMGUI_DIR}/imgui.cpp
)

target_include_directories( imgui
                            PUBLIC ${IMGUI_DIR}
                            PUBLIC ${IMGUI_DIR}/backends
                            PUBLIC ${SDL2_DIR}/include
)
