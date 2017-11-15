cmake_minimum_required(VERSION 3.0.0) #Not sure if this is accurate
project (FPL_ImGui)

add_executable(FPL_ImGui FPL_ImGui/main.cpp FPL_ImGui/dependencies/imgui/include/imgui/imgui.cpp)
include_directories(../ ./FPL_ImGui/dependencies/imgui/include)
