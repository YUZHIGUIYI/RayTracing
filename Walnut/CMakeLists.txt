file(GLOB_RECURSE WalnutFiles CONFIGURE_DEPENDS include/*.h src/*.cpp)

add_library(Walnut STATIC ${WalnutFiles})

target_include_directories(Walnut PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)
target_include_directories(Walnut PUBLIC ${Vulkan_INCLUDE_DIRS})
target_include_directories(Walnut PUBLIC ${PROJECT_SOURCE_DIR}/external/glm)
target_include_directories(Walnut PUBLIC ${PROJECT_SOURCE_DIR}/external/stb)

target_link_libraries(Walnut PUBLIC ImGui)
target_link_libraries(Walnut PUBLIC glfw)
target_link_libraries(Walnut PUBLIC ${Vulkan_LIBRARIES})

target_compile_definitions(Walnut PUBLIC WL_PLATFORM_WINDOWS)