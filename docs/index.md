# Welcome to Bia

For full documentation visit [mkdocs.org](https://mkdocs.org).

## Building

### Prerequisites

- [CMake](https://cmake.org/) at least Version 3.1
- C++ Compiler with at least C++11 support
- Git

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

## Configuration

## Compiling

### Getting the Source Code

```bash
git clone https://github.com/terrakuh/Bia.git
mkdir Bia/build
cd Bia/build
```

### Building

```bash
cmake .. -DCMAKE_BUILD_TYPE=Release
cmake --build .
```

### Testing

```bash
ctest
```

### Installing

```bash
cmake --build . --target install
```
