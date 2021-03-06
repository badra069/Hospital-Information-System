cmake_minimum_required(VERSION 3.5)

project(Code LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# QtCreator supports the following variables for Android, which are identical to qmake Android variables.
# Check http://doc.qt.io/qt-5/deployment-android.html for more information.
# They need to be set before the find_package(Qt5 ...) call.

#if(ANDROID)
#    set(ANDROID_PACKAGE_SOURCE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/android")
#    if (ANDROID_ABI STREQUAL "armeabi-v7a")
#        set(ANDROID_EXTRA_LIBS
#            ${CMAKE_CURRENT_SOURCE_DIR}/path/to/libcrypto.so
#            ${CMAKE_CURRENT_SOURCE_DIR}/path/to/libssl.so)
#    endif()
#endif()

find_package(Qt5 COMPONENTS Widgets REQUIRED)

if(ANDROID)
  add_library(Code SHARED
    main.cpp
    mainwindow.cpp
    database.cpp
    database.h
    queue.cpp
    queue.h
    heap.cpp
    heap.h
    mainwindow.h
    mainwindow.ui
    addnewpatient.cpp
    addnewpatient.h
    addnewpatient.ui
    addnewdoctor.cpp
    addnewdoctor.h
    addnewdoctor.ui
    addnewicu.cpp
    addnewicu.h
    addnewicu.ui
    addnewprescription.cpp
    addnewprescription.h
    addnewprescription.ui
    viewdoctor.cpp
    viewdoctor.h
    viewdoctor.ui
    viewicu.cpp
    viewicu.h
    viewicu.ui
    viewpatient.cpp
    viewpatient.h
    viewpatient.ui
    viewprescription.cpp
    viewprescription.h
    viewprescription.ui
  )
else()
  add_executable(Code
    main.cpp
    mainwindow.cpp
    database.cpp
    database.h
    queue.cpp
    queue.h
    heap.cpp
    heap.h
    mainwindow.h
    mainwindow.ui
    addnewpatient.cpp
    addnewpatient.h
    addnewpatient.ui
    addnewdoctor.cpp
    addnewdoctor.h
    addnewdoctor.ui
    addnewicu.cpp
    addnewicu.h
    addnewicu.ui
    addnewprescription.cpp
    addnewprescription.h
    addnewprescription.ui
    viewdoctor.cpp
    viewdoctor.h
    viewdoctor.ui
    viewicu.cpp
    viewicu.h
    viewicu.ui
    viewpatient.cpp
    viewpatient.h
    viewpatient.ui
    viewprescription.cpp
    viewprescription.h
    viewprescription.ui
  )
endif()

target_link_libraries(Code PRIVATE Qt5::Widgets)
