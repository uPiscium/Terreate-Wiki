# Intro
There are many properties that the window has like its position or size. In this section, we'll see the callbacks of it and how to use it. 

# Contents
- [x] Use window callbacks with custom events

# Hook with window callbacks
```cpp
#include <Terreate/Terreate.hpp>

bool Frame(Terreate::Context *ctx) {
  ctx->Fill(0, 0, 0);
  ctx->Clear();
  ctx->Swap();
  return true;
}

int main() {
  Terreate::ContextHandler handler;
  auto context = handler.CreateContext(800, 600, "Terreate guide");

  auto keycallback = 

  context->Run(Frame);

  while (handler->IsRunning()) {
    handler->PollEvents();
  }
  return 0;
