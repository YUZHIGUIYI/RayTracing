file(GLOB_RECURSE WalnutFiles CONFIGURE_DEPENDS include/*.h src/*.cpp)

add_library(Walnut STATIC ${WalnutFiles})

target_include_directories(Walnut PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)
target_include_directories(Walnut PUBLIC ${Vulkan_INCLUDE_DIRS})
target_include_directories(Walnut PUBLIC ${PROJECT_SOURCE_DIR}/external/glm)
target_include_directories(Walnut PUBLIC ${PROJECT_SOURCE_DIR}/external/stb)

target_link_libraries(Walnut PUBLIC ImGuiDocking)
target_link_libraries(Walnut PUBLIC glfw)
target_link_libraries(Walnut PUBLIC ${Vulkan_LIBRARIES})

if(${WALNUT_BUILD_WIN32})
    target_compile_definitions(Walnut PUBLIC WL_PLATFORM_WINDOWS)
else()
    message(FATAL_ERROR "Walnut only supports Windows platform")
endif()