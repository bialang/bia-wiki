# Operators

## Precedence

The following table shows Bia's operator precedence from highest to lowest.

| Operator                                         | Description                             | Associativity |
| ------------------------------------------------ | --------------------------------------- | ------------- |
| `a.b`,`a()`,`a[]`                                | member access, function call, subscript | left-to-right |
| `**`                                             | exponentiation                          |               |
| `-a`, `~a`                                       | unary minus, bitwise not                | right-to-left |
| `*`, `/`, `%`                                    | multiplication, division and remainder  | left-to-right |
| `+`, `-`                                         | addition and subtraction                |               |
| `<<`, `>>`                                       | bitwise shift                           |               |
| `in`, `not in`, `<`, `>`, `<=`, `>=`, `!=`, `==` | including test and comparisons          |               |
| `&`                                              | bitwise and                             |               |
| `^`                                              | bitwise xor                             |               |
| `|`                                              | bitwise or                              |               |
| `and`                                            | logical and                             |               |
| `or`                                             | logical or                              |               |
| `not`                                            | logical not                             | right-to-left |
