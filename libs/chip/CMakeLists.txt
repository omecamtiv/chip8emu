project(chip)

add_library(
    ${PROJECT_NAME}
    STATIC
    src/chip.cpp
)

add_library(
    library::chip
    ALIAS
    ${PROJECT_NAME}
)

target_include_directories(
    ${PROJECT_NAME}
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include
)