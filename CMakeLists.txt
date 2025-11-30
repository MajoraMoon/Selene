cmake_minimum_required(VERSION 3.16)
project(Selene LANGUAGES C CXX)


# Set the C++ standards and similar
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Dependencies (in Core/lib)
# include(Dependencies_lib.cmake)

include_directories(${PROJECT_SOURCE_DIR}/Core/lib)

add_subdirectory(Core)
add_subdirectory(Selene)

message(STATUS "")
message(STATUS "Configuration Summary:")
message(STATUS "  Project: Selene")
message(STATUS "  C++ Standard: ${CMAKE_CXX_STANDARD}")
message(STATUS "  Compiler: ${CMAKE_CXX_COMPILER_ID}")
message(STATUS "  CXX Flags: ${CMAKE_CXX_FLAGS}")
message(STATUS "  Output Directory: ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}")
