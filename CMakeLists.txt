cmake_minimum_required(VERSION 3.16)

<<<<<<< HEAD
project(untitled VERSION 0.1 LANGUAGES CXX)
=======
project(test VERSION 0.1 LANGUAGES CXX)
>>>>>>> 3e97dda6124f7246cb8508139d8e15d44a04d796

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Widgets)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Widgets)

set(PROJECT_SOURCES
        main.cpp
        mainwindow.cpp
        mainwindow.h
        mainwindow.ui
)

if(${QT_VERSION_MAJOR} GREATER_EQUAL 6)
<<<<<<< HEAD
    qt_add_executable(untitled
=======
    qt_add_executable(test
>>>>>>> 3e97dda6124f7246cb8508139d8e15d44a04d796
        MANUAL_FINALIZATION
        ${PROJECT_SOURCES}
    )
# Define target properties for Android with Qt 6 as:
<<<<<<< HEAD
#    set_property(TARGET untitled APPEND PROPERTY QT_ANDROID_PACKAGE_SOURCE_DIR
=======
#    set_property(TARGET test APPEND PROPERTY QT_ANDROID_PACKAGE_SOURCE_DIR
>>>>>>> 3e97dda6124f7246cb8508139d8e15d44a04d796
#                 ${CMAKE_CURRENT_SOURCE_DIR}/android)
# For more information, see https://doc.qt.io/qt-6/qt-add-executable.html#target-creation
else()
    if(ANDROID)
<<<<<<< HEAD
        add_library(untitled SHARED
=======
        add_library(test SHARED
>>>>>>> 3e97dda6124f7246cb8508139d8e15d44a04d796
            ${PROJECT_SOURCES}
        )
# Define properties for Android with Qt 5 after find_package() calls as:
#    set(ANDROID_PACKAGE_SOURCE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/android")
    else()
<<<<<<< HEAD
        add_executable(untitled
=======
        add_executable(test
>>>>>>> 3e97dda6124f7246cb8508139d8e15d44a04d796
            ${PROJECT_SOURCES}
        )
    endif()
endif()

<<<<<<< HEAD
target_link_libraries(untitled PRIVATE Qt${QT_VERSION_MAJOR}::Widgets)
=======
target_link_libraries(test PRIVATE Qt${QT_VERSION_MAJOR}::Widgets)
>>>>>>> 3e97dda6124f7246cb8508139d8e15d44a04d796

# Qt for iOS sets MACOSX_BUNDLE_GUI_IDENTIFIER automatically since Qt 6.1.
# If you are developing for iOS or macOS you should consider setting an
# explicit, fixed bundle identifier manually though.
if(${QT_VERSION} VERSION_LESS 6.1.0)
<<<<<<< HEAD
  set(BUNDLE_ID_OPTION MACOSX_BUNDLE_GUI_IDENTIFIER com.example.untitled)
endif()
set_target_properties(untitled PROPERTIES
=======
  set(BUNDLE_ID_OPTION MACOSX_BUNDLE_GUI_IDENTIFIER com.example.test)
endif()
set_target_properties(test PROPERTIES
>>>>>>> 3e97dda6124f7246cb8508139d8e15d44a04d796
    ${BUNDLE_ID_OPTION}
    MACOSX_BUNDLE_BUNDLE_VERSION ${PROJECT_VERSION}
    MACOSX_BUNDLE_SHORT_VERSION_STRING ${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}
    MACOSX_BUNDLE TRUE
    WIN32_EXECUTABLE TRUE
)

include(GNUInstallDirs)
<<<<<<< HEAD
install(TARGETS untitled
=======
install(TARGETS test
>>>>>>> 3e97dda6124f7246cb8508139d8e15d44a04d796
    BUNDLE DESTINATION .
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

if(QT_VERSION_MAJOR EQUAL 6)
<<<<<<< HEAD
    qt_finalize_executable(untitled)
=======
    qt_finalize_executable(test)
>>>>>>> 3e97dda6124f7246cb8508139d8e15d44a04d796
endif()
