# Hello, World

This examples demonstrates how to bind a simple C++ function to an engine and then executing a small script.

```cpp
#include <bia/engine.hpp>
#include <bia/bsl/io.hpp>
#include <iostream>
#include <sstream>

int main()
{
  bia::Engine engine;
  engine.function("hello_world", 
    +[] { std::cout << "Hello, World! - C++\n"; });
  engine.module("io", bia::bsl::io);

  std::stringstream code;
  code << u8R"(
    // prints 'Hello, World' to the console
    import io
    io.print("Hello, World! - Bia")

    // calls the C++ function and
    // print 'Hello, World - C++' to the console
    hello_world()
  )";

  engine.execute(code);
}
```
