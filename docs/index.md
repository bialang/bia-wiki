# Welcome to Bia

For full documentation visit [mkdocs.org](https://mkdocs.org).

## Dependencies

No dependency is actually required, however, the **bold** printed dependecies are recommended and enabled by default.

| Dependency                              | Usage                      | Configuration                    |
| --------------------------------------- | -------------------------- | -------------------------------- |
| **[ICU](http://site.icu-project.org/)** | String encoding conversion | BIA_STRING_ENCODING_BACKEND=ICU  |
| **[MPIR](http://mpir.org/)**            | Integrated big numbers     | BIA_BIG_INT_BACKEND=MPIR         |
| **[PCRE2](#)**                          |                            | BIA_REGEX_BACKEND=PCRE2          |
| [std::regex](#)                         |                            | BIA_REGEX_BACKEND=std::regex     |
| [boost::regex](#)                       |                            | BIA_REGEX_BACKEND=boost::regex   |
| **[std::thread](#)**                    |                            | BIA_THREAD_BACKEND=std::thread   |
| [boost::thread](#)                      |                            | BIA_THREAD_BACKEND=boost::thread |

### Required for Testing

[Catch2]([#](https://github.com/catchorg/Catch2)) is required for testing and is in the repository included (no additional cloning).

## Building from Source

Prerequisites:

- [CMake](https://cmake.org/) at least Version 3.1
- C++ Compiler with at least C++11 support
- Git

The source code can be retrieved from GitHub with ❤

```bash
git clone https://github.com/bialang/bia.git
mkdir bia/build
cd bia/build
```

With CMake and the source code, the library can be build as follows:

```bash
cmake .. -DCMAKE_BUILD_TYPE=Release
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
