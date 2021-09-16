# Cheatsheet

## The Engine
A Bia engine can be initialized like this:

=== "C++"

    ```cpp
    #include <bia/engine.hpp>

    bia::Engine engine;
    ```

## Executing a Script

The `execute()` function of the engine takes a `std::istream` for the script. It compiles and runs the code immediately:

=== "C++"

    ```cpp
    #include <fstream>

    std::ifstream file{ "myscript.bia" };
    engine.execute(file);
    ```

## Language Reference

### Variables

```bia
let x = 0
let x: int = 0

x = 1 // 'x' is immutable
let mut x = 0
x = 0 // is now accepted

drop x // 'x' is now unkown
```

### Scopes

```bia
scope {
    let x = 0
}
print(x) // 'x' is undefined
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

### Conditionals

```Bia
if x and not y {
    io.print(x)
} else if y {
    io.print(y)
}
```
