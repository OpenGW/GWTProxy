
cmake_minimum_required (VERSION 3.1 FATAL_ERROR)

project (
    GWTProxy
    VERSION 0.1.0
    LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 14)


# Generate configuration file
configure_file(
    "src/config.h.in"
    "configured/config.h"
    ESCAPE_QUOTES
    @ONLY)
include_directories("${CMAKE_CURRENT_BINARY_DIR}/configured")

# Add gwtproxy executable
set (SOURCE_FILES "src/main.cxx")

add_executable (gwtproxy ${SOURCE_FILES})
