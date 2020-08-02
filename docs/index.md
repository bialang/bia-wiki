# Welcome to Bia

## Dependencies

No dependency is actually required, however, the **bold** printed dependecies are recommended and enabled by default.

| Dependency  | Usage | Configuration                  | Default                   |
| ----------- | ----- | ------------------------------ | ------------------------- |
| std::thread |       | BIA_THREAD_BACKEND=std::thread | *default* and recommended |

### Required for Testing

[Catch2]([#](https://github.com/catchorg/Catch2)) is required for testing and is in the repository included (no additional cloning).

## Building from Source

Prerequisites:

- CMake *(version 3.1)*
- C++ compiler with at least C++11 support
- git

The source code can be retrieved from [GitHub](https://github.com/bialang/bia) with ❤

```bash
git clone https://github.com/bialang/bia.git
mkdir bia/build
cd bia/build
```

With CMake and the source code, the library can be build as follows:

```bash
cmake ..
cmake --build .
```

We recommend running the test before installing the library:

```bash
ctest
```

If every test passed, everthing is good to go and the following command can be run (elevated privileges may be required). However, if any test failed, please open an issue on GitHub.

```bash
cmake --build . --target install
```
