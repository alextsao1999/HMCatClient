cmake_minimum_required(VERSION 2.8)

project(HMCatClient)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_PREFIX_PATH  "F:/Qt/5.8/mingw53_32/lib/cmake")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY  ${CMAKE_BINARY_DIR})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY   ${CMAKE_BINARY_DIR})
add_subdirectory(third_party/quickjs)
add_executable(quickjstest test.cpp)
target_link_libraries(quickjstest quickjs)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)
set(USE_QT Core Gui Widgets)
find_package(Qt5 COMPONENTS ${USE_QT} REQUIRED)
add_executable(hmcat main.cpp mainwindow.cpp mainwindow.h mainwindow.ui)
qt5_use_modules(hmcat ${USE_QT})


