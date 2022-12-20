cmake_minimum_required(VERSION 3.15 FATAL_ERROR)

project(Walnut LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED OFF)
set(CMAKE_CXX_EXTENSIONS ON)

if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/bin)

# Vulkan
find_package(Vulkan REQUIRED)
if(${Vulkan_FOUND})
    message(STATUS "Vulkan Include Directories: ${Vulkan_INCLUDE_DIRS}")
    message(STATUS "Vulkan Library Libraries: ${Vulkan_LIBRARIES}")
endif()

# glfw
add_subdirectory(external/glfw)

# imgui
add_subdirectory(external/imgui)

# Walnut library
add_subdirectory(Walnut)

# Walnut App - a example to use Walnut library
add_subdirectory(WalnutApp)
