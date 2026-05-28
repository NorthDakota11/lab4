# lab04

Continuous integration laboratory work for a CMake C++ project.

The task is based on `tp-labs/lab04`. The original lab asks to configure CI for the CMake project from lab03: Travis CI on Linux with gcc and clang, and AppVeyor on Windows.

## Project

This repository contains the `print` static library from lab03:

- `include/print.hpp` - public header
- `sources/print.cpp` - implementation
- `CMakeLists.txt` - build and install rules
- `.travis.yml` - Travis CI configuration placeholder
- `appveyor.yml` - AppVeyor configuration placeholder

## Local build

```sh
cmake -S . -B _build -DCMAKE_INSTALL_PREFIX=_install
cmake --build _build
cmake --build _build --target install
```

## Required Travis CI configuration

Use this full `.travis.yml` content if editing manually:

```yaml
language: cpp

os: linux
dist: focal

compiler:
  - gcc
  - clang

script:
  - cmake -S . -B _build -DCMAKE_INSTALL_PREFIX=_install
  - cmake --build _build
  - cmake --build _build --target install
```

## Required AppVeyor configuration

Use this full `appveyor.yml` content if editing manually:

```yaml
image: Visual Studio 2019

build_script:
  - cmake -S . -B _build -DCMAKE_INSTALL_PREFIX=_install
  - cmake --build _build --config Release
  - cmake --build _build --config Release --target install
```
