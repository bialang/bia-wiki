# Hello, World

This examples demonstrates how to bind a simple C++ function to an engine and then executing a small script.

```cpp
#include <bia/bia.hpp>
#include <iostream>

inline void hello_world()
{
	std::cout << "Hello, World! - C++\n";
}

int main()
{
	bia::engine eng;

	eng.fun("hello_world", &hello_world);

	eng.execute(R"(
		import io

		let name = "Bia"

		io.puts(f"Hello, World! - {name}")
		hello_world()
	)");
}
```
