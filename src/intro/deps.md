## Library dependence
Here's the packages that are used in this library.
- [glfw](https://www.glfw.org/docs/latest/)
  > GLFW is a free, Open Source, multi-platform library for OpenGL, OpenGL ES and Vulkan application development. It provides a simple, platform-independent API for creating windows, contexts and surfaces, reading input, handling events, etc.\
\
*from glfw website*
- [glad](https://glad.dav1d.de/)
  > Multi-Language GL/GLES/EGL/GLX/WGL Loader-Generator based on the official specs.\
\
*from glad website*
- [OpenAL-soft](https://github.com/kcat/openal-soft.git)
  > OpenAL Soft is an LGPL-licensed, cross-platform, software implementation of the OpenAL 3D audio API. It's forked from the open-sourced Windows version available originally from openal.org's SVN repository (now defunct). OpenAL provides capabilities for playing audio in a virtual 3D environment. Distance attenuation, doppler shift, and directional sound emitters are among the features handled by the API. More advanced effects, including air absorption, occlusion, and environmental reverb, are available through the EFX extension. It also facilitates streaming audio, multi-channel buffers, and audio capture.\
\
*from OpenAL-soft README.md*

## Build dependence
This library uses `cmake` to build the projects so make sure to install `cmake` before building this library. 

## X11/Wayland dependence(*on Linux*)
If you are using X11/Wayland environment, these packages are needed to build and execute.\
(Package names might be different in package managers. The names listed below are example in **`apt`**)
- libwayland-bin
- libwayland-dev
- wayland-protocols
- libxkbcommon-dev
- libx11-dev
- libxrandr-dev
- libxinerama-dev
- libxcursor-dev
- libxi-dev

Note:
> If you are using `nix` package manager and `direnv`, dependence installing is automatically executed.
