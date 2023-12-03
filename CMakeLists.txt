cmake_minimum_required(VERSION 3.16)
project(AntonOpenGL4Tuto LANGUAGES CXX)

set(INSTALL_PROJECTDIR "D:/Software/Programming/Projects/antonopengl4tuto/bin")
set(TARGET_NAME "AntonOpenGL4Tuto")

find_package(Qt6 REQUIRED COMPONENTS Core Gui OpenGL)

qt_standard_project_setup()

qt_add_executable(${TARGET_NAME}
    src/main.cpp
    src/openglwindow.cpp src/openglwindow.h
    src/trianglewindow.h src/trianglewindow.cpp
    shaders/shaders.qrc
)

set_target_properties(${TARGET_NAME} PROPERTIES
    WIN32_EXECUTABLE TRUE
    RUNTIME_OUTPUT_DIRECTORY "${INSTALL_PROJECTDIR}"
    CMAKE_RUNTIME_OUTPUT_DIRECTORY "${INSTALL_PROJECTDIR}"
)

target_link_libraries(${TARGET_NAME} PRIVATE
    Qt6::Core
    Qt6::Gui
    Qt6::OpenGL
)

install(TARGETS ${TARGET_NAME}
    RUNTIME DESTINATION "${INSTALL_PROJECTDIR}"
)
