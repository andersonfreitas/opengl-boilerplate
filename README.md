# OpenGL C++ Boilerplate

A cross-platform boilerplate project for OpenGL using GLFW and GLEW in C++. Compilation is done with `cmake`

## Cloning

The `external/` contains all the depencies used, but they are tracked using git submodules. In order to compile the program, you should first clone the repository and then download the dependencies with `git submodule init` and `git submodule update`

Alternatively, with can achieve this in a one-line as follows:

    git clone git@github.com:andersonfreitas/opengl-minimal-cpp.git --recursive

## Initializing GLEW

Before compiling, you should first generate the `include/` folder for GLFW:

    cd external/glew
    make extensions

## Build

Create a folder `build` and then run `make`

## Using different dependency versions

If you want to use a different version of any dependency tracked as a submodule, you just need to checkout the desired in the repository:

    cd external/my_dep
    git checkout XXX
    cd ..
    git add external/my_dep
    git commit -m "Using my_dep at branch/tag XXX"

## Dependencies

 * [GLFW](https://github.com/glfw/glfw)
 * [GLEW](http://github.com/nigels-com/glew.git)
 * [GLM](https://github.com/g-truc/glm)
