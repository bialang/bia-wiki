# Getting Started

After installing Bia it can be used in your CMake projects:

```cmake
find_package(bialang REQUIRED)

add_executable(main "main.cpp")
target_link_libraries(main PUBLIC bialang::bialang)
```

For simple embedding including `<bia/bia.hpp>` and using `bia::engine` should be enough.
