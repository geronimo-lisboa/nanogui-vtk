cmake_minimum_required(VERSION 2.8)
#nome do projeto
project(nanogui-vtk)
#Seta os paths das coisas necessárias
set(VTK_DIR "C:/libs/VTK-8.0.0_bin")#vtk
#pega os arquivos
file(GLOB my_source_files "*.h" "*.cpp")
#Define um executável
add_executable(teste ${my_source_files} )
# Find VTK
find_package(VTK REQUIRED)
include(${VTK_USE_FILE})
target_link_libraries(teste ${VTK_LIBRARIES})
#nanogui
include_directories("C:/Program Files/NanoGUI/include")
target_link_libraries(teste "C:/Program Files/NanoGUI/lib/nanogui.lib")
include_directories("C:/libs/nanogui/ext/eigen")
include_directories("C:/libs/nanogui/ext/coro")
include_directories("C:/libs/nanogui/ext/glad/include")
include_directories("C:/libs/nanogui/ext/glfw/include")
include_directories("C:/libs/nanogui/ext/nanovg/src")
include_directories("C:/libs/glew-2.1.0/include")

target_link_libraries(teste "C:/libs/glew-2.1.0/lib/Release/x64/glew32.lib")


