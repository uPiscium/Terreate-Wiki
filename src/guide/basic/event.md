## Section overview
- [x] Use event handler of `Context`
- [x] Retrieve window associated events via `Event`.
- [x] Use pub-sub event system

## Review the last section
In the last section, ["Create a Window"](./window.md), we created a simple base app that shows only black blank window. The code that we created is shown below. 
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
