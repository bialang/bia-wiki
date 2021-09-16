# Welcome to Bia
Bia is a statically and strongly typed programming language. The primary goal is to be able to embed it into C++ applications. There are also plans for C and Go ports. The second goal is to be a readable and intuitive language.

## Dependencies
Bia does not need any dependencies apart from a C++11 compatible compiler and the standard library.

### Required for Testing

[Catch2]([#](https://github.com/catchorg/Catch2)) is required for testing and is in the repository included (no additional cloning).

## Building from Source
Prerequisites:

- CMake *(version 3.1)*
- C++ compiler with at least C++11 support
- git

The source code can be retrieved from [GitHub](https://github.com/bialang/bia).

```sh
git clone https://github.com/bialang/bia.git
mkdir bia/build && cd bia/build
```

With CMake and the source code, the library can be build as follows:

```sh
cmake ..
cmake --build .
```

We recommend running the test before installing the library:

```sh
ctest
```

If every test passed, everthing is good to go and the following command can be run (elevated privileges may be required). However, if any test failed, please open an issue on GitHub.

```sh
cmake --build . --target install
```
