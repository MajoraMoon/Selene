cmake_minimum_required(VERSION 3.16)
project(Selene LANGUAGES C CXX)


# Set the C++ standards and similar
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# exetuable directory (later load textures etc outside of executable)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

file(MAKE_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

# Dependencies (in Core/lib)
# include(Dependencies_lib.cmake)

add_subdirectory(Core)
add_subdirectory(Selene)


add_custom_target(copy_bin ALL
    COMMAND ${CMAKE_COMMAND} -E copy_if_different
        ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/Selene${CMAKE_EXECUTABLE_SUFFIX}
        ${CMAKE_SOURCE_DIR}/bin/
    COMMENT "Copying executable to ${CMAKE_SOURCE_DIR}/bin/"
    DEPENDS Selene
)


message(STATUS "")
message(STATUS "Configuration Summary:")
message(STATUS "  Project: Selene")
message(STATUS "  C++ Standard: ${CMAKE_CXX_STANDARD}")
message(STATUS "  Compiler: ${CMAKE_CXX_COMPILER_ID}")
message(STATUS "  CXX Flags: ${CMAKE_CXX_FLAGS}")
message(STATUS "  Output Directory: ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}")
