cmake_minimum_required(VERSION 3.16.0)

aux_source_directory(. SRC_LIST)

set(BACKENDS_DIR backends)

add_library(
    imgui
    SHARED
    ${SRC_LIST}
    ${BACKENDS_DIR}/imgui_impl_glfw.cpp
    ${BACKENDS_DIR}/imgui_impl_opengl3.cpp
)

target_include_directories(imgui PUBLIC .)

target_link_libraries(
    imgui
    glfw
)

set_target_properties(imgui PROPERTIES OUTPUT_NAME "imgui")
