cmake_minimum_required(VERSION 3.0.0) #Not sure if this is accurate

project (FPL_ImGui)
add_executable(FPL_ImGui    FPL_ImGui/main.cpp
                            FPL_ImGui/dependencies/imgui/include/imgui/imgui.cpp
                            FPL_ImGui/dependencies/imgui/include/imgui/imgui_draw.cpp
                            FPL_ImGui/dependencies/imgui/include/imgui/imgui_demo.cpp
)
target_include_directories(FPL_ImGui PUBLIC ../ ./FPL_ImGui/dependencies/imgui/include)

if(UNIX)
    target_link_libraries(FPL_ImGui GL X11)
elseif(WIN32)
    target_link_libraries(FPL_ImGui opengl32)
endif()

project (FOGL_Test)
add_executable(FOGL_Test FOGL_Test/main.cpp)
target_include_directories(FOGL_Test PUBLIC ../)

project(FPL_Console)
add_executable(FPL_Console FPL_Console/main.cpp)
target_include_directories(FPL_Console PUBLIC ../)

project(FPL_OpenGL)
add_executable(FPL_OpenGL FPL_OpenGL/main.cpp)
target_include_directories(FPL_OpenGL PUBLIC ../ FPL_OpenGL/dependencies/glew/include/)

project(FTT_TileTracingDemo)
add_executable(FTT_TileTracingDemo FTT_TileTracingDemo/main.cpp)
target_include_directories(FTT_TileTracingDemo PUBLIC ../)
