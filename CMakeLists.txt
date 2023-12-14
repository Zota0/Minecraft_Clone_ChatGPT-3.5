# CMakeList.txt : CMake project for Minecraft_clone, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project ("Minecraft_clone")

# Add source to this project's executable.
add_executable (Minecraft_clone "Minecraft_clone.cpp" "Minecraft_clone.h" "src/main.cpp")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET Minecraft_clone PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.

# Include directories
include_directories(include) # your headers are in the 'include' folder

# Find and include external libraries (SDL2, GLFW, etc.)
find_package(SDL2 REQUIRED)
find_package(GLFW REQUIRED)
# Add other necessary libraries similarly

# Add subdirectories for different parts of your project
add_subdirectory(src)
# Add other directories (tests, additional modules, etc.) if needed