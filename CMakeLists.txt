cmake_minimum_required(VERSION 3.22)

project(wxMFC)

find_package(wxwidgets CONFIG REQUIRED)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

add_definitions(-D_AFXDLL -D_WIN32_WINNT=_WIN32_WINNT_WIN7 -DWINVER=_WIN32_WINNT_WIN7)
set(CMAKE_MFC_FLAG 2)

add_executable(wxMFC WIN32
    mfctest.h
    mfctest.cpp
    mfctest.ico
    mfctest.rc
    resource.h
    stdafx.h
    vcpkg.json
)
target_link_libraries(wxMFC PUBLIC wx::core wx::base)
set_property(TARGET wxMFC PROPERTY VS_DPI_AWARE "OFF")
