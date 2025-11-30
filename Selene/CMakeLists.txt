# Cmake for Selenes main source files


set(SOURCES
    src/Main.cpp)

add_executable(Selene ${SOURCES})

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR})

target_link_libraries(Selene PRIVATE Core)

target_include_directories(Selene PRIVATE ${PROJECT_SOURCE_DIR}/Selene/src)
target_include_directories(Selene PRIVATE ${PROJECT_SOURCE_DIR})

# precompiled headers
target_precompile_headers(Selene PRIVATE
    $<$<COMPILE_LANGUAGE:CXX>:${PROJECT_SOURCE_DIR}/Selenepch.h>
)
