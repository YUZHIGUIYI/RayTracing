# RayTracing

## Introduction
- The Walnut API is cloned from [TheCherno](https://github.com/TheCherno) Project [Walnut](https://github.com/TheCherno/Walnut), 
  but it is built with [CMake](https://cmake.org/) for my personal will.

- This is my personal practice in RayTracing via [Vulkan SDK](https://vulkan.lunarg.com/sdk/home#windows).

## Requirements
- [Visual Studio 2022](https://visualstudio.com)
- [Vulkan SDK](https://vulkan.lunarg.com/sdk/home#windows)

## Usage
```shell
cmake -B build 
cmake --build build --config=Release
./bin/WalnutApp
```

### Third party libaries
- [GLFW](https://github.com/glfw/glfw)
- [GLM](https://github.com/g-truc/glm)
- [Dear ImGui](https://github.com/ocornut/imgui)
- [stb](https://github.com/nothings/stb)