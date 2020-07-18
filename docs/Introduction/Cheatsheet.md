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

#### Condition Based

```bia
while true {
	let line = io.read("> ")

	if not line {
		break
	}

	io.print("< You said:", line)
}
```

#### Range Loops

```bia
for i in range(10) {
	io.print(i)
}

for m in /\d+/.match_all("18.07.2020") {
	io.print(m.group(0))
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
