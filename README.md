# OpenGL C++ Boilerplate

A cross-platform boilerplate project for OpenGL using GLFW and GLEW in C++. Compilation is done with `cmake`.

I want to keep this project as simple as possible and is targetted to those who are learning modern OpenGL.

## Cloning

The `external/` folder contains all the external dependencies used, and they are tracked using git submodules. In order to compile the program, you should first clone the repository and then download the dependencies with `git submodule init` and `git submodule update`

Alternatively, you can achieve this with a one-liner as follows:

    git clone git@github.com:andersonfreitas/opengl-boilerplate.git --recursive

## Initializing GLEW

Before compiling, you should first generate the `include/` folder for GLFW:

    cd external/glew
    make extensions

## Build

    mkdir build && cd build
    cmake ..
    make

### Building with XCode

    mkdir xcode && cd xcode
    cmake -G "Xcode" ..

Then open the generated `Project.xcodeproj` project.

If you don't have CMake installed on your Mac, the easist way is to install is with [Homebrew](http://brew.sh) using `brew install cmake`

### Building with Visual Studio

CMake comes with a diverse options of [generators](http://www.cmake.org/cmake/help/v2.8.8/cmake.html#section_Generators). Use the CMake GUI on Windows to automatically create a project solution based on this project.

## Using a different dependency version

If you want to use a different version of any dependency tracked as a submodule, you just need to checkout the desired version in the repository:

    cd external/my_dep
    git checkout XXX
    cd ..
    git add external/my_dep
    git commit -m "Using my_dep at branch/tag XXX"

## Dependencies

 * [GLFW](https://github.com/glfw/glfw)
 * [GLEW](http://github.com/nigels-com/glew.git)
 * [GLM](https://github.com/g-truc/glm)
 * [CMake](http://www.cmake.org/)
