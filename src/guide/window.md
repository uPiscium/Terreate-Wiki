## Contents
- [x] Create context handler
- [x] Create context object
- [x] Handling window with context object
- [x] Use simple frame callback

## Create window
The first thing we need to do is create an application window. In `Terreate`, windows are controlled by ***Context*** objects. Each context object has one glfw window object, and you can control it through the context object. Contexts also have its own thread called *Context thread*, which is used to run a rendering function, called *frame function*, in each frame.
![window description image](../images/guide/window-description.png)

To create a context object, you have to create ***ContextHandler*** object. ContextHandler manages the context state and the context thread.
![context handler description image](../images/guide/context-handler-description.png)

