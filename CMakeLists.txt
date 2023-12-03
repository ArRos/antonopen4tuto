# Copyright (C) 2022 The Qt Company Ltd.
# SPDX-License-Identifier: BSD-3-Clause

cmake_minimum_required(VERSION 3.16)
project(AntonOpenGL4Tuto LANGUAGES CXX)

set(INSTALL_PROJECTDIR "D:/Software/Programming/Projects/AntonOpenGL4Tuto/bin")

find_package(Qt6 REQUIRED COMPONENTS Core Gui OpenGL)

qt_standard_project_setup()

qt_add_executable(openglwindow
    src/main.cpp
    src/openglwindow.cpp src/openglwindow.h
    src/trianglewindow.h src/trianglewindow.cpp
)

set_target_properties(openglwindow PROPERTIES
    WIN32_EXECUTABLE TRUE
)

target_link_libraries(openglwindow PRIVATE
    Qt6::Core
    Qt6::Gui
    Qt6::OpenGL
)

install(TARGETS openglwindow
    RUNTIME DESTINATION "${INSTALL_PROJECTDIR}"
    BUNDLE DESTINATION "${INSTALL_PROJECTDIR}"
    LIBRARY DESTINATION "${INSTALL_PROJECTDIR}"
)
