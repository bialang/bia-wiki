# Getting Started

After installing Bia it can be used in your CMake projects:

```cmake
find_package(bia REQUIRED)

add_executable(main "main.cpp")
target_link_libraries(main PUBLIC bia::bia)
```

For simple embedding in C++ including `<bia/bia.hpp>` and using `bia::engine` should be enough. For the C Port including `<bia/cbia.h>` and using `bia_engine_t` should be enough.

## Go

!!! warning
    This package has not been updated. Do not use it yet.

```sh
go get github.com/bialang/gobia
```

!!! note
    You will need to have Bia installed on your machine in order to be able to use this interface.
