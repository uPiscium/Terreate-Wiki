## Section overview
- [x] Window representation
- [x] Simple game loop

In this section, we will create our first simplest application. It is only a blank black window.

## Create `Context`
First, we need to create a manager of `Terreate`, called `Context`. `Context` is a manager for all resources or resource handlers that are used in the program. The first thing we need to do is create a `Context` class instance:
```cpp
#include "Terreate/Terreate.hpp"

int main() {
  Terreate::Context context;
  return 0;
}
```
Once you execute the program above, you will see that the program immediately terminates and returns code 0.

## Create `Window`
Next, we need to create a `Window` to represent our awesome app. Windows are created by the createWindow() function, which is a method of the Context class:
```cpp
#include "Terreate/Terreate.hpp"

int main() {
  Terreate::Context context;

  auto window = context.createWindow(700, 500, "My first window");
  // or
  // Terreate::shared<Terreate::Window> window = context.createWindow(700, 500, "My first window");

  return 0;
}
```
If you execute this code, you may see a black window for a moment.

# Define *Mainloop*
In the current code, we cannot see our awesome app due to the life time of the window. Now, we will add *Mainloop* that keeps the window and other objects in our app alive until the app terminates.
```cpp
#include "Terreate/Terreate.hpp"

int main() {
  ...

  while (context.valid()) {
    window->fill(0.85, 0, 0);
    window->clear();

    window->update();
    context.tick(120);
  }

  return 0;
}
```
Now, we can see the black blank window in front of us!

# Links
- [*Prev - Index of "The basics"*](../basic.md)
- [*Next - 1.2. Handle events*](./events.md)
