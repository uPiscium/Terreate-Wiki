# Handle events
## Section overview
- [x] Use event handler of `Context`
- [x] Retrieve window associated events via `Event`.
- [x] Use pub-sub event system

## Review the last section
In the last section, ["Create a Window"](./window.md), we created a simple base app that shows only a black blank window. The code that we created is shown below. 
```cpp
#include "Terreate/Terreate.hpp"

int main() {
  Terreate::Context context;

  auto window = context.createWindow(700, 500, "My first window");

  while (context.valid()) {
    window->fill(0.85, 0, 0);
    window->clear();

    window->update();
    context.tick(120);
  }

  return 0;
}
```
In this section, we will handle some events that is associated to window. 

## Get event handler
The first thing we need to do is to get an event handler from the `Context`:
```cpp
...

int main() {
  ...

  auto window = context.createWindow(700, 500, "My first window");
  auto event = context.getEventHandler();

  ...
}
```
`EventHandler` has various events that is essential to create applications like mouse, clipboard, keyboard, text input(including IME), and more! If you want to know more about the events, see [Event type documentation](../../docs/event/type.md) for more information.

## Subscribe to an event
Earlier we got the event handler from the context, but this is not enough to get the event itself - in order to get the event, we need to register a callback to the event:
```cpp
#include <Terreate/Terreate.hpp>
#include <iostream>

int main() {
  ...

  auto event = context.getEventHandler();

  auto mousePosCallback = [](u64 timestamp, shared<Window> window, shared<Mouse> mouse, vec2 const &pos, vec2 const &rel) {
    std::cout << "Mouse moved to: (" << pos.x << ", " << pos.y << ")" << std::endl;
  };
  event->onMouseMotion.subscribe(mousePosCallback);

  ...
}
```
This code outputs the mouse position when the mouse cursor is moved. Let's take a look at this step by step. First, we get a handler from context. Next, we define the callback for retrieving the event. The arguments of function is defined for each event type. This is shown in the [Event callback type documentation](../../docs/event/callback.md).
Finally, we called `subscribe` to register the callback to event.

<div class="warning">
If you want to retrieve one of the event instances and not interested in other instances that comes after the retrieved event, you should use `trigger` instead of `subscribe`.
</div>
