# Running a c++ application from mac's terminal vs-code

## Youtube video link: https://youtu.be/kXhRAVb0Ol0

## GitHub repo link: https://github.com/Shendidy/hello_world-cpp.git

To get started after installing vs-code, make sure to install the add-on c/c++:


Name: C/C++
Id: ms-vscode.cpptools
Description: C/C++ IntelliSense, debugging, and code browsing.
Version: 0.23.1
Publisher: Microsoft
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools


Then create your app.cpp file, and create a tasks.json file inside the .vscode folder and paste the following code in it then save it:

```
/* tasks.json */
{
  "version": "2.0.0",
  "tasks": [
      {
          "label": "build",
          "command": "clang++",
          "args": [
              "-o",
              "run", // executable
              "hello_world.cpp", // main file
              "-g",
              "-v"
          ],
          "type": "shell",
          "presentation": {
              "echo": true,
              "reveal": "always",
              "panel": "shared"
          },
          "problemMatcher": {
              "owner": "cpp",
              "fileLocation": [
                  "relative",
                  "${workspaceRoot}"
              ],
              "pattern": {
                  "regexp": "^(.*):(\\d+):(\\d+):\\s+(warning|error):\\s+(.*)$",
                  "file": 1,
                  "line": 2,
                  "column": 3,
                  "severity": 4,
                  "message": 5
              }
          }
      }
  ]
}
```

In the line where I wrote "run" for the executable, you can choose any other command you want to use to run the application from the terminal. and in the line below it specify the file to open when you run the app.

When you have a code to compile and run, click command+shift+B, and click 'build' from the list at the top, then in your terminal, go to the folder where tha app.cpp is saved and type:

```
./run
```
This should run the application for you in the terminal.

Reference:

https://medium.com/gdplabs/build-and-debug-c-on-visual-studio-code-for-mac-77e05537105e

