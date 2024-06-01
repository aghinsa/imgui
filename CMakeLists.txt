cmake_minimum_required(VERSION 3.5)
project(ImGui)


# Set where the ImGui files are stored
set(IMGUI_PATH  ".")
    
# Compile as static library 
file(GLOB IMGUI_SOURCES ${IMGUI_PATH}/*.cpp) 
add_library("ImGui" ${IMGUI_LIBRARY_TYPE} ${IMGUI_SOURCES})

#backend is included when Steins/src/platform/openGL/imgui_impl_opengl3.cpp was copied
# TODO: remove later?
target_include_directories("ImGui" PUBLIC ${IMGUI_PATH} ${IMGUI_PATH}/backends)