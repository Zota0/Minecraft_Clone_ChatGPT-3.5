# Set up rendering-specific module
project(MyRenderingModule)

set(SOURCES
    rendering.cpp
    # Add more source files as needed
)

set(HEADERS
    rendering.h
    # Add more header files as needed
)

add_library(RenderingModule ${SOURCES} ${HEADERS})

# Include directories
target_include_directories(RenderingModule PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# Link any necessary external libraries (SDL2, GLFW, etc.)
target_link_libraries(RenderingModule PUBLIC SDL2::SDL2 GLFW::GLFW)

find_package(SDL2 REQUIRED)
find_package(GLFW REQUIRED)

# Include SDL2 and GLFW
add_subdirectory(lib/SDL2)
add_subdirectory(lib/GLFW)

# Add other external libraries similarly
