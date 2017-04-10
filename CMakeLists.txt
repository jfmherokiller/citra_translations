cmake_minimum_required(VERSION 3.2)
project(citra_translations)
find_package(Git REQUIRED)
find_package(Qt5 REQUIRED COMPONENTS Core LinguistTools)

# For some external project macros
include(ExternalProject)
# setup citra as an external project to allow it to always be up to date
ExternalProject_Add(
        citra
        PREFIX ${CMAKE_SOURCE_DIR}/citra
        GIT_REPOSITORY https://github.com/citra-emu/citra.git
        GIT_TAG "master"
        BUILD_COMMAND "true"
        CONFIGURE_COMMAND "true"
        INSTALL_COMMAND "true"
        UPDATE_COMMAND ${GIT_EXECUTABLE} pull --rebase -f
)
#citra_qt files
file(GLOB_RECURSE CITRA_UI citra/src/citra/src/citra_qt/*.ui )
file(GLOB_RECURSE CITRA_SRC citra/src/citra/src/citra_qt/*.cpp )
file(GLOB_RECURSE CITRA_HDR citra/src/citra/src/citra_qt/*.h )

add_subdirectory(translations)