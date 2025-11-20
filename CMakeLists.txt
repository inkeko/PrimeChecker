cmake_minimum_required(VERSION 3.16)
set(QT_VERSION_MAJOR 6)
project(PrimeChecker VERSION 0.1 LANGUAGES CXX)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 REQUIRED COMPONENTS Widgets)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Widgets)

set(SOURCES
    main.cpp
    gui/mainwindow.cpp
    gui/resultform.cpp
    src/primechecker.cpp
)

set(HEADERS
    gui/mainwindow.h
    gui/resultform.h
    src/primechecker.h
)

set(UIS
    ui/mainwindow.ui
    ui/resultform.ui
)
qt_add_executable(PrimeChecker
    ${SOURCES}
    ${HEADERS}
    ${UIS}
)



