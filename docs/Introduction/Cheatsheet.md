# Cheatsheet

## The Engine
A Bia engine can be initialized like this:

=== "C++"
    ```cpp
    #include <bia/bia.hpp>

    bia::engine engine;
    ```

=== "C"
    ```c
    #include <bia/cbia.h>

    bia_engine_t engine = bia_engine_new();
    // always free afterwards
    bia_engine_free(engine);
    ```

=== "Go"
    ```go
    import "github.com/bialang/gobia"

    engine, err := gobia.NewEngine()
    if err != nil {
        panic(err)
    }
    defer engine.Close()
    ```

## Executing a Script

The `bia::engine::execute` function takes a `std::istream` for the script:

```C++ tab=
#include <fstream>

std::ifstream file{ "myscript.bia" };
engine.execute(file);
```

## Language Reference

### Variables

```Bia
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

```Bia
for i in range(10) {
    io.print(i)
}

for m in r"\d+".match_all("18.07.2020") {
    io.print(m.group(0))
}
```

### Conditionals

```Bia
if x and not y {
    io.print(x)
} else if y {
    io.print(y)
}
```
