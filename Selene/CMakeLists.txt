# Cmake for Selenes main source files

set(SOURCES
    src/Main.cpp)

add_executable(Selene ${SOURCES})

target_link_libraries(Selene PRIVATE Core)

target_include_directories(Selene PRIVATE ${PROJECT_SOURCE_DIR}/Selene/src
    ${PROJECT_SOURCE_DIR})

# precompiled headers
target_precompile_headers(Selene PRIVATE
    $<$<COMPILE_LANGUAGE:CXX>:${PROJECT_SOURCE_DIR}/Selenepch.h>
)
