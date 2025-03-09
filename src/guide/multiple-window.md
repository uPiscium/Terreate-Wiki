## Intro
In first section, we created a single window application. In this section, we'll create a multi-window application. If you forget the window handling, see [Create a window](./window.md) section.

## Contents
- [x] Multiple windows with different frame function

## Multi-window
As I mentioned in the [Create a window section](./window.md), contexts have its own thread. So we can simply duplicate the first step code to handle the multiple windows.
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
