# https://github.com/microsoft/vscode-cmake-tools/blob/main/docs/README.md
# 

cmake_minimum_required(VERSION 3.29.2)
project(PamuxCPP VERSION 0.1.0 LANGUAGES C CXX)

# Find dependencies provided by vcpkg (via vcpkg.cmake)
find_package(fmt CONFIG REQUIRED)



add_executable(PamuxCPP )

target_sources(PamuxCPP PRIVATE src/private/main.cpp)
target_link_libraries(PamuxCPP PRIVATE fmt::fmt-header-only)
set_property(TARGET PamuxCPP PROPERTY CXX_STANDARD 23)

