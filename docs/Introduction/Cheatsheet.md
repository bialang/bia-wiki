# Cheatsheet

## The Engine

A Bia engine can be initialized like this:

```cpp
#include <bia/bia.hpp>

bia::engine engine;
```

## Executing a Script

The `bia::engine::execute` function takes a `std::istream` for the script:

```cpp
#include <fstream>

std::ifstream file{ "myscript.bia" };

engine.execute(file);
```

## Language Reference

### Variables

```bia
let x = 0

let x = null // x is deleted
```

### Looping

```bia
while true {
	let line = io.read("> ")

	if not line {
		break
	}

	io.print("< You said:", line)
}
```

### Conditionals

```bia
if x and not y {
	io.print(x)
} else if y {
	io.print(y)
}
```
