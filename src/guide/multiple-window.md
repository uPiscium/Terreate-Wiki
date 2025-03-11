## Intro
In first section, we created a single window application. In this section, we'll create a multi-window application. If you forget the window handling, see [Create a window](./window.md) section.

## Contents
- [x] Multiple windows with different frame function

## Multi-window
As I mentioned in the [Create a window section](./window.md), contexts have its own thread. So you can simply duplicate the first step code to handle the multiple windows.
```cpp
#include <Terreate/Terreate.hpp>

bool FrameRed(Terreate::Context *ctx) {
  auto *window = ctx->window;
  window->Fill(0.8, 0.0, 0);
  window->Clear();
  window->Swap();
  return true;
}

bool FrameGreen(Terreate::Context *ctx) {
  auto *window = ctx->window;
  window->Fill(0, 0.8, 0);
  window->Clear();
  window->Swap();
  return true;
}


bool FrameBlue(Terreate::Context *ctx) {
  auto *window = ctx->window;
  window->Fill(0, 0, 0.5);
  window->Clear();
  window->Swap();
  return true;
}

int main() {
  Terreate::ContextHandler handler;
  auto red_context = handler.CreateContext(800, 600, "Red screen");
  auto green_context = handler.CreateContext(800, 600, "Green screen");
  auto blue_context = handler.CreateContext(800, 600, "Blue screen");

  red_context->Run(FrameRed);
  green_context->Run(FrameGreen);
  blue_context->Run(FrameBlue);

  while (handler->IsRunning()) {
    handler->PollEvents();
  }
  return 0;
}
```

Now, if you build and run this program, you will see three windows filled with red, green, and blue. In this example, the different contexts are handled by corresponding frame functions. **Make sure that each thread implementation is thread-safe.**

## Next step
- [Use multi-thread executor](guide/executor.md)
