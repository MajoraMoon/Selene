# Core Application Base

set(CORE_SOURCES
    src/Test.cpp
    )

set(GLAD_SRC ${PROJECT_SOURCE_DIR}/Core/lib/glad/src/glad.c)
set_source_files_properties(${GLAD_SRC} PROPERTIES LANGUAGE C)

add_library(Core STATIC ${CORE_SOURCES} ${GLAD_SRC})

target_include_directories(Core PUBLIC ${CMAKE_SOURCE_DIR}/Core/src
    ${CMAKE_SOURCE_DIR}/Core/lib/glad/include)




# Compiler features and options (I think I should remove the Cmake standard in the main cmake)
target_compile_features(Core PUBLIC cxx_std_23)
