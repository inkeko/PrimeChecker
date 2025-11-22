cmake_minimum_required(VERSION 3.16)
project(PrimeChecker VERSION 0.1 LANGUAGES CXX)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(QT_VERSION_MAJOR 6)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Widgets)

set(SOURCES
    main.cpp
    src/mainwindow.cpp
    src/resultform.cpp
    src/primechecker.cpp
)

set(HEADERS
    src/mainwindow.h
    src/resultform.h
    src/primechecker.h
)

set(UIS
    ui/mainwindow.ui
    ui/resultform.ui
)

qt_add_executable(PrimeChecker
    MANUAL_FINALIZATION
    ${SOURCES}
    ${HEADERS}
    ${UIS}
)

target_link_libraries(PrimeChecker PRIVATE Qt6::Widgets)

qt_finalize_executable(PrimeChecker)