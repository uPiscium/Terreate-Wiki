## Intro
In some video games, like fps or open world, we can control player character with joystick or gamepad. In this section, we'll handle joystick and gamepad inputs.

## Contents
- [x] Get the device connecting state
- [x] Identify the input device
- [x] Get joystick and gamepad state

## Handle joystick and gamepad
Like many other objects in Terreate, joystick and gamepad also have wrapper class. You can get its states through it.
```cpp
#include <Terreate/Terreate.hpp>
#include <iostream>

bool Frame(Terreate::Context *ctx) {
  ctx->Fill(0, 0, 0);
  ctx->Clear();

  auto joystick = Terreate::Joystick::GetJoystick(JoystickID::JOYSTICK1);

  if (!joystick.IsConnected()) {
    std::cout << "Disconnected" << std::endl;
    return true;
  }

  auto axes = joystick.GetAxisState();
  auto buttons = joystick.GetButtonState();
  auto hats = joystick.GetHatState();

  std::cout << "Left Stick: (" << std::fixed << std::setprecision(3)
     << axisState.leftStick[0] << ", " << axisState.leftStick[1] << ")" << " / Right Stick: (" << std::fixed << std::setprecision(3)
     << axisState.rightStick[0] << ", " << axisState.rightStick[1] << ")" << std::endl;
  std::cout << std::fixed << std::setprecision(3)
     << "Left Trigger: " << axisState.leftTrigger
     << " / Right Trigger: " << axisState.rightTrigger << std::endl;

  std::cout << "A: " << buttonState.a << " / B: " << buttonState.b
     << " / X: " << buttonState.x << " / Y: " << buttonState.y << std::endl;
  std::cout << " / Cross: " << buttonState.cross << " / Circle: " << buttonState.circle
     << " / Square: " << buttonState.square
     << " / Triangle: " << buttonState.triangle << std::endl;

  std::cout << "Left Bumper: " << buttonState.leftBumper
     << " / Right Bumper: " << buttonState.rightBumper
     << " / Back: " << buttonState.back << " / Start: " << buttonState.start
     << " / Guide: " << buttonState.guide
     << " / Left Thumb: " << buttonState.leftThumb
     << " / Right Thumb: " << buttonState.rightThumb << std::endl;

  std::cout << "D-Pad: Up: " << buttonState.dpadUp
     << " / Right: " << buttonState.dpadRight
     << " / Down: " << buttonState.dpadDown
     << " / Left: " << buttonState.dpadLeft << std::endl;

  std::cout << "Hat: Up: " << hatState.up << " / Right: " << hatState.right
     << " / Down: " << hatState.down << " / Left: " << hatState.left << std::endl;

  ctx->Swap();
}

int main() {
  Terreate::ContextHandler handler;
  auto context = handler.Create(800, 600, "Joystick and Gamepad test");

  context->Run(Frame);
  while (handler.IsRunning()) {
    glfwPollEvents();
  }
  return 0;
}
```
Now, build your project and run your application file, you will see the states of joystick or gamepad if you connect it in command line. Otherwise, there are only a word "Disconnected".
