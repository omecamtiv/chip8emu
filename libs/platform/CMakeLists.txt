project(platform)

find_package(SDL2 REQUIRED)

add_library(
    ${PROJECT_NAME}
    STATIC
    src/platform.cpp
)

add_library(
    library::platform
    ALIAS
    ${PROJECT_NAME}
)

target_include_directories(
    ${PROJECT_NAME}
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include
    ${SDL2_INCLUDE_DIRS}
)

target_link_libraries(
    ${PROJECT_NAME}
    ${SDL2_LIBRARIES}
)