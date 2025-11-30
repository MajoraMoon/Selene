# CelestiaCore - Build Instructions

## Requirements

- **CMake** (version 3.15 or higher)
- **A compiler** (e.g. `gcc`)
- **Make** or **Ninja**


The build has been tested on:
- **Linux** (Arch-based) using `gcc` / `g++`
- **Windows** with MinGW & MSYS2

#### MSYS2 Requirements
If compiling with **MSYS2**, these packages are probably needed.  
Without them, the compiler may try to build a Linux (X11/Wayland) version instead of a Windows one:

```sh
pacman -S --needed base-devel mingw-w64-x86_64-toolchain mingw-w64-x86_64-cmake mingw-w64-x86_64-ninja
```

## How to build and compile

```bash

git clone https://github.com/MajoraMoon/SelenEcplise.git
cd SelenEclipse

mkdir build
cd build

cmake ..

# Then either make or ninja
make
```

For faster compilation (may stress your CPU):

      cmake --build . --parallel


**Run the Executable**

   After building, run the program with:

   ```bash
   ../bin/SelenEcplise
   ```
