# Flow Control

## Conditionals

### `if`, `else if` and `else`

```bia
if x {
    io.print("x evaluates to true")
} else if not y {
    io.print("x and y evaluate to false")
} else {
    io.print("why am i here")
}
```

## Loops

### `while`

```bia
while x {
    io.print(x)
    if not y {
        break
    }
    x = y.something()
}
```

### `for...in`

```Bia
for i in range(10) {
    io.print(i)
}
```

In this case the variable `i` will be declared only for the loop and will not be available outside of the scope. If a variable already existed with the same name, it will be overshadowed.
