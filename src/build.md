## Build preparation
**Make sure you have the [cmake](https://cmake.org/) installed before building.**\
In this example, build outputs are stored in `<REPOSITRY ROOT DIR>/build/` folder.\
(If you don't want to build tests, use `cmake -S . -B build -DBUILD_TERREATE_TEST=off` instead of `cmake -S . -B build` command.)

## NixOS(or `nix` installed environment)
### with `direnv`
```shell
cd <PATH TO CLONED/UNZIPPED REPOSITORY>
cmake -S . -B build
cmake --build build
```

### without `direnv`
```shell
cd <PATH TO CLONED/UNZIPPED REPOSITORY>
nix develop
cmake -S . -B build
cmake --build build
```

## Linux
**Make sure you have the dependencies installed before building.**
```shell
cd <PATH TO CLONED/UNZIPPED REPOSITORY>
cmake -S . -B build
cmake --build build
```

## Windows
```shell
cd <PATH TO CLONED/UNZIPPED REPOSITORY>
cmake -S . -B build
cmake --build build
```

## MacOS
***Currently, MacOS is not officially supported.***
```shell
cd <PATH TO CLONED/UNZIPPED REPOSITORY>
cmake -S . -B build
cmake --build build
```
