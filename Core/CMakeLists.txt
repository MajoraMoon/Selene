# Core Application Base

add_subdirectory(lib/glad)

set(CORE_SOURCES
    src/Test.cpp
    )


add_library(Core STATIC ${CORE_SOURCES})

target_include_directories(Core PUBLIC ${CMAKE_SOURCE_DIR}/Core/src
  )


target_link_libraries(Core PUBLIC glad)

# Compiler features and options (I think I should remove the Cmake standard in the main cmake)
target_compile_features(Core PUBLIC cxx_std_23)
