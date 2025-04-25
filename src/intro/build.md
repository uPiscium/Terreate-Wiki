# Building project
**Make sure you installed [cmake](https://cmake.org/) before building.**

## Build outputs
In this example, build outputs are stored in `<REPOSITRY ROOT DIR>/build/` folder.\

## `Cmake` options
### `TERREATE_BUILD_TEST`
Default: ON

Specifies whether to build test code.

### `TERREATE_DEBUG_BUILD`
Default: OFF

Specifies whether to build in debug mode. In debug mode, `TERREATE_DEBUG_MODE` is defined.

## Windows & Linux
**Make sure you installed dependencies before building.**
```shell
cmake -S . -B build
cmake --build build
```

## `nix` installed env
```shell
nix develop // if you have direnv this line is not needed.
cmake -S . -B build
cmake --build build
```

## [Next - ***]()
