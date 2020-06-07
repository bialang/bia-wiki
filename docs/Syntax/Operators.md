# Operators

## Special Behavior of the Logical Operators

### Logical And

If the left-hand side can be converted to `true`, the right-hand side is returned; otherwise the left-hand side is returned:

```bia
io.print(99 and 61) // 61
io.print(0 and 61) // 0
```

### Logical Or

If the left-hand side can be converted to `true`, it is returned; otherwise the right-hand side is returned:

```bia
io.print(99 or 61) // 99
io.print(0 or 61) // 61
```

## Precedence

The following table shows Bia's operator precedence from highest to lowest.

| Operator                               | Description                             | Associativity |
| -------------------------------------- | --------------------------------------- | ------------- |
| `a.b`,`a()`,`a[]`                      | member access, function call, subscript | left-to-right |
| `**`                                   | exponentiation                          |               |
| `-a`, `~a`                             | unary minus, bitwise not                | right-to-left |
| `*`, `/`, `%`                          | multiplication, division and remainder  | left-to-right |
| `+`, `-`                               | addition and subtraction                |               |
| `<<`, `>>`                             | bitwise shifts                          |               |
| `&`                                    | bitwise and                             |               |
| `^`                                    | bitwise xor                             |               |
| `|`                                    | bitwise or                              |               |
| `<=>`                                  | three-way comparison                    |               |
| `in`, `<`, `>`, `<=`, `>=`, `!=`, `==` | including test and comparisons          |               |
| `not`                                  | logical not                             | right-to-left |
| `and`                                  | logical and                             |               |
| `or`                                   | logical or                              |               |
