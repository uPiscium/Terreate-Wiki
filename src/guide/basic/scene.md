# Create a Scene
## Section overview
- [x] Create the root Scene of app
- [x] Create a Renderer for rendering scene
- [x] Use renderer in the `mainloop`

## Review the last section
In the last section, ["Handle Events"](./event.md), we created a simple base app with the window and event handler. The code that we created is shown below.
```cpp
#include "Terreate/Terreate.hpp"

int main() {
  Terreate::Context context;

  auto window = context.createWindow(700, 500, "My first window");
  auto event = context.getEventHandler();

  auto mousePosCallback = [](u64 timestamp, shared<Window> window, shared<Mouse> mouse, vec2 const &pos, vec2 const &rel) {
    std::cout << "Mouse moved to: (" << pos.x << ", " << pos.y << ")" << std::endl;
  };
  event->onMouseMotion.subscribe(mousePosCallback);

  while (context.valid()) {
    window->fill(0, 0, 0);
    window->clear();

    window->update();
    context.tick(120);
  }

  return 0;
}
```
In this section we will create a scene that is used to put the entities to render and create a renderer to render the scene. 

## Create a Scene
First, we start by creating a scene through a context:
```cpp
...

int main() {
  ...

  auto window = context.createWindow(700, 500, "My first window");
  auto event = context.getEventHandler();
  auto scene = context. createScene("My first scene");

  ...
}
```
When we create a scene we should give it a name, which is used to retrieve the same scene from different places in our code.

## Create a Renderer
