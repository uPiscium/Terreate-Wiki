## Section overview
- [x] Window representation
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
Next, we need to create a `Window` to represent our awesome app. `Window` is created by `createWindow()` function defined as `Context` class method.
```cpp
#include "Terreate/Terreate.hpp"

int main() {
  Terreate::Context context("Terreate guide", Terreate::Type::Version{0, 1, 0});

  auto window = context->createWindow("My first window", {700, 500});

  return 0;
}
```
