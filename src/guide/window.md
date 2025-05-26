## Features in this section
- [x] Create `Context`
- [x] Create `Pipeline`
- [x] Create `Framebuffer`
- [x] Window representation
- [x] Simple game loop

In this section, we will create our first simplest application. It is only a blank black window.

## Overview


## Create `Context`
First, we need to create a manager of `Terreate`, called `Context`. `Context` manages the resources that are used in the program. The first thing we need to do is create a `Context` class instance:
```cpp
#include "Terreate/Terreate.hpp"

int main() {
  Terreate::Context context;

  return 0;
}
```

## 
