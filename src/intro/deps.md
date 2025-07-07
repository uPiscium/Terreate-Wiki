## Library dependency
Here's the packages that are used in this library.

- [SDL](https://www.libsdl.org/)
  > Simple DirectMedia Layer is a cross-platform development library designed to provide low level access to audio, keyboard, mouse, joystick, and graphics hardware via OpenGL and Direct3D. It is used by video playback software, emulators, and popular games including Valve's award winning catalog and many Humble Bundle games.
  > SDL officially supports Windows, macOS, Linux, iOS, and Android. Support for other platforms may be found in the source code.
  > SDL is written in C, works natively with C++, and there are bindings available for several other languages, including C# and Python.
  > SDL is distributed under the zlib license. This license allows you to use SDL freely in any software.\
  *from SDL website*
- [glad](https://glad.dav1d.de/)
  > Multi-Language GL/GLES/EGL/GLX/WGL Loader-Generator based on the official specs.\
  *from glad website*

## Build Dependency
This library uses `cmake` to build the projects so make sure to install `cmake` before building this library. 

### on Windows
There is no additional dependence to build this library on Windows.

### on Linux
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

> [!NOTE]
> If you are using `nix` package manager and `direnv`, dependence installing is automatically executed.

## Links
- [*Prev - What is Terreate?*](./terreate.md)
- [*Next - Build project*](./build.md)
