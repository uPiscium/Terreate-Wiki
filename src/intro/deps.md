## Library dependence
Here's the packages that are used in this library.

- [Vulkan](https://www.vulkan.org/)
  > Vulkan is not a company, nor language, but rather a way for developers to program their modern GPU hardware in a cross-platform and cross-vendor fashion. The Khronos Group is a member-driven consortium that created and maintains Vulkan.\
  *from Vulkan documentation*

- [glfw](https://www.glfw.org/docs/latest/)
  > GLFW is a free, Open Source, multi-platform library for OpenGL, OpenGL ES and Vulkan application development. It provides a simple, platform-independent API for creating windows, contexts and surfaces, reading input, handling events, etc.\
  *from glfw website*

- [OpenAL-soft](https://github.com/kcat/openal-soft.git)
  > OpenAL Soft is an LGPL-licensed, cross-platform, software implementation of the OpenAL 3D audio API. It's forked from the open-sourced Windows version available originally from openal.org's SVN repository (now defunct). OpenAL provides capabilities for playing audio in a virtual 3D environment. Distance attenuation, doppler shift, and directional sound emitters are among the features handled by the API. More advanced effects, including air absorption, occlusion, and environmental reverb, are available through the EFX extension. It also facilitates streaming audio, multi-channel buffers, and audio capture.\
  *from OpenAL-soft README.md*

## Build dependence
This library uses `cmake` to build the projects so make sure to install `cmake` before building this library. 

### on Windows
Install [Vulkan SDK](https://www.lunarg.com/vulkan-sdk/)

> [Vulkan tutorial - Development environment](https://vulkan-tutorial.com/Development_environment) explains how to set it up in detail.

### with `apt`
Install packages below.
- vulkan-tools
- libvulkan-dev
- vulkan-validationlayers-dev
- spirv-tools

### with `dnf`
Install packages below.
- vulkan-tools
- vulkan-loader-devel
-  mesa-vulkan-devel
-  vulkan-validation-layers-devel

### with `pacman`
Install `vulkan-devel` package.

## [Next - Build project](./build.md)
