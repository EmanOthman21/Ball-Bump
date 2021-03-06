
## Steps to run on your computer

1. Install [Node.js](https://nodejs.org/en/) and [Visual Studio Code](https://code.visualstudio.com/).
2. Open this lab folder in Visual Studio Code.
3. Open a terminal (Terminal > New Terminal).
4. run `npm install` . If it failed for any reason, try again.
5. run `npm run watch` .
6. Ctrl + click the link shown in the terminal (usually it will be http://localhost:1234).
## To run on web
go to this link https://muhammeedalaa.github.io/Ball-Bump/
**Note:** controls is 'A' to move left 'D' to move right

**Note:** you can use yarn to enable caching so that you don't download all the packages with project. You can download yarn from [yarnpkg.com](https://yarnpkg.com/lang/en/). Then replace `npm install` with `yarn install` and `npm run watch` with `yarn watch`.

**Debugging:** You will need the extension [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome). After running till Step 5 from [Steps to run](#steps-to-run), press F5 or click the Debug icon on the left bar then choose *"Launch Chrome against"* localhost" and click the *"Start Debugging"* button (play button). Now you can use breakpoints, watch, etc. The required configuration for the debugger is written in `.vscode/launch.json`.

## Game Structure

**index.html** is the webpage in which we run our app. It is the entry point of our app and it links to the main script file "app.ts"

**app.ts** is the entry point of our code. It just initializes the game object, sets the scenes and fills the scene selector. It can be considered as the equivalent of the main function in C++.

**game.ts** contains the *Game* class and the abstract *Scene* class. The game class is responsible for creating the WebGL2 context, running the game loop, managing scenes and running other helper classes such as the *Input* class and the *Loader* class. The *Scene* class is the base class of all the other scenes.

**Loader.ts** and **input.ts** contain helper classes that handles fetching data from the webserver and capturing the user input.

**shader-program.ts** contains the *ShaderProgram* class which contains some boilerplate code to loading shaders. It will be used extensively in every scene so we isolated it into a reusable class from the start.

**mesh.ts** contains some boilerplate code for creating VAOs and VBOs. You can also use **mesh-utils.ts** to create some basic shapes (Rectangle, Cube).

**camera.ts** contains a camera class to manage the variables for a camera. It can be used with one of the **camera-controllers** to create user-controlled camera.

**scenes folder** contains the scenes that demonstrate some concepts we need to understand about WebGL2.

**static folder** contains the assets file for our project. It currently contains the shader files in the **shaders folder**.

