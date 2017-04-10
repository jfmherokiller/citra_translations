cmake_minimum_required(VERSION 3.7)
project(citra_translations)
find_package(Qt5 REQUIRED COMPONENTS Core LinguistTools)

#citra_qt files
file(GLOB_RECURSE CITRA_UI citra/src/citra_qt/*.ui )
file(GLOB_RECURSE CITRA_SRC citra/src/citra_qt/*.cpp )
file(GLOB_RECURSE CITRA_HDR citra/src/citra_qt/*.h )

add_subdirectory(translations)