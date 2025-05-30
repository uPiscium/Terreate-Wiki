## Section overview
- [x] Window representation
- [x] Rendering with renderer
- [x] Simple game loop

In this section, we will create our first simplest application. It is only a blank black window.

## Create `Context`
First, we need to create a manager of `Terreate`, called `Context`. `Context` manages the resources that are used in the program. The first thing we need to do is create a `Context` class instance:
```cpp
#include "Terreate/Terreate.hpp"

int main() {
  Terreate::Context context("Terreate guide", Terreate::Type::Version{0, 1, 0});

  return 0;
}
```

## Create `Window`
Next, we need to create a `Window` to represent our awesome app. Windows are created by the createWindow() function, which is a method of the Context class:
```cpp_diff
#include "Terreate/Terreate.hpp"

int main() {
  Terreate::Context context("Terreate guide", Terreate::Type::Version{0, 1, 0});

+  auto window = context.createWindow("My first window", {700, 500});
  // or
  // Terreate::VkObj<Terreate::Window> window = context.createWindow("My first window", {700, 500});

  return 0;
}
```

# Create `Renderer`
Now, we have window to represent contents, but don't have renderer to render it. So in this step, we will create a `Renderer`. Renderers are created by the createRenderer() function, which is a method of the Context class same as `Window`:
```cpp_diff
#include "Terreate/Terreate.hpp"

int main() {
  Terreate::Context context("Terreate guide", Terreate::Type::Version{0, 1, 0});

  auto window = context.createWindow("My first window", {700, 500});
+  auto renderer = context. createRenderer();

  return 0;
}
```
