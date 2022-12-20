file(GLOB_RECURSE WalnutAppFiles CONFIGURE_DEPENDS src/*.h src/*.cpp)

add_executable(WalnutApp ${WalnutAppFiles})

target_link_libraries(WalnutApp PRIVATE Walnut)

# Since we have previously defined in Walnut - A "PUBLIC" property
# target_compile_definitions(WalnutApp PRIVATE WL_PLATFORM_WINDOWS)

