# Compiling PSXFunkin

## Setting up the Development Environment
First off, you'll need a terminal one way or another.

Follow the PSn00bSDK set up instructions here https://github.com/spicyjpeg/PSn00bSDK/blob/master/doc/installation.md

You also need to download Ninja from [HERE](https://github.com/ninja-build/ninja/releases) and put it on your PATH, or install it with your package manager. On Windows, this can be as simple as copying the ninja.exe file into your PSn00bSDK/bin folder, or even your CMake/bin folder.

## Compiling PSXFunkin
First, make sure to `cd` to the repo directory where the CMakeLists.txt is. You're gonna want to run a few commands from here;

this will build the tools.
`cmake -S ./tools -B ./tools/build -G "Ninja"` 
`cmake --build ./tools/build`

this builds the game itself.
`cmake -S . -B ./build -G "Ninja" -DCMAKE_TOOLCHAIN_FILE=C:\PSn00bSDK\lib\libpsn00b\cmake\sdk.cmake` Replace C:\PSn00bSDK with the path you put PSn00bSDK in.
(add -DCMAKE_BUILD_TYPE=Debug at the end to build for debug mode) 
`cmake --build ./build` 

You can read more about the asset formats in [FORMATS.md](/FORMATS.md)

If everything went well, you should have a `funkin.bin` and a `funkin.cue` in the build directory.
