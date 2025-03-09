## Intro
In this section, we'll create a simple single window application.

## Contents
- [x] Create context handler
- [x] Create context object
- [x] Handling window with context object
- [x] Use simple frame callback

## Window, Context, Context handler
The first thing we need to do is create an application window. In `Terreate`, windows are controlled by ***Context*** objects. Each context object has one glfw window object, and you can control it through the context object. Contexts also have its own thread called *Context thread*, which is used to run a rendering function, called *frame function*, in each frame.
![window description image](../images/guide/window-description.png)

To create a context object, you have to create ***ContextHandler*** object. ContextHandler manages the context state and the context thread.
![context handler description image](../images/guide/context-handler-description.png)

Now, let's code!

## Create window
```cpp
#include <Terreate/Terreate.hpp>

bool Frame(Terreate::Context *ctx) {
  auto *window = ctx->window;
  window->Fill(0.5, 0.5, 0);
  window->Clear();
  window->Swap();
  return true;
}

int main() {
  Terreate::ContextHandler handler;
  auto context = handler.CreateContext(800, 600, "Terreate guide");

  context->Run(Frame);

  while (handler->IsRunning()) {
    handler->PollEvents();
  }
  return 0;
}
```
First, we see the `Frame` function, but we'll skip it for now. After that, `main` is defined.

In the first line of the `main` function, line 12, a `ContextHandler` instance is created. Then, we create a new context via the `handler` variable. 

The `CreateContext` function is a builder function for the `Context` class and takes the following arguments: `width`, `height`, and `title`. For more information about this function, see the [Window API](../api/window.md) section.

Moving on to the next step: On line 15, the context starts the rendering thread using `Frame` as its *frame function*. Let's take a look at the steps in the `Frame` function:
1. Fill the window with yellow. (rgb(0.5, 0.5, 0))
1. Clear the window buffer
1. Swap the window buffer
This is a minimal implementation of the *frame function*.

Finally, lines 17 to 19 run an event polling loop on the main thread until the application stops.

Now, build your project and run your application file, you will see a window filled with yellow in front of you.
![yellow window](../images/guide/yellow-window.png)

## Next step
[Draw polygons](./draw-poly.md)
