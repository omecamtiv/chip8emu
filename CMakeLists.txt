cmake_minimum_required(VERSION 3.7)

project(chip8emu)

set(chip8emu_VERSION_MAJOR 0)
set(chip8emu_VERSION_MINOR 1)
set(chip8emu_VERSION_PATCH 0)
set(chip8emu_VERSION "${chip8emu_VERSION_MAJOR}.${chip8emu_VERSION_MINOR}.${chip8emu_VERSION_PATCH}")

add_subdirectory(libs/chip)
add_subdirectory(libs/platform)

add_executable(
    chip8
    src/main.cpp
)

target_link_libraries(
    chip8
    library::chip
    library::platform
)

install(
    TARGETS
    chip8
    DESTINATION
    bin
)

set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Chip-8 Emulator")
set(CPACK_PACKAGE_VENDOR "Omecamtiv")
set(CPACK_RESOURCE_FILE_README ${CMAKE_CURRENT_SOURCE_DIR}/README.md)
set(CPACK_RESOURCE_FILE_LICENSE ${CMAKE_CURRENT_SOURCE_DIR}/LICENSE)
set(CPACK_PACKAGE_VERSION ${chip8emu_VERSION})
set(CPACK_SOURCE_GENERATOR TGZ)
set(CPACK_SOURCE_IGNORE_FILES "/build/")

include(CPack)