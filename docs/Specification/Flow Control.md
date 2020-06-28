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
