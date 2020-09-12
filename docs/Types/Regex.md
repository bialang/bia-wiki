# Native Regular Expressions

## Syntax

The pattern must be wrapped between `r"` and `"` like following:

```Bia
let pattern = r"ab+"
```

## Examples

```Bia
// matches any digit
let pattern = r"\d+"

io.print(pattern == "65") // 1
io.print(pattern in "some string") // 0
io.print(pattern in "i am 21 years old") // 1
io.print(pattern.match("i am 21 years old")) // <null>
io.print(pattern.search("i am 21 years old").group(0)) // 21

for i in pattern.match_all("18.07.2020") {
    io.print(i.group(0))
}
```

## Modifiers

!!! warning "This has not been implemented yet"

Modifiers come immediately after the regex without any spaces:

```Bia
let pattern = r"a.+"si
```

| Modifier | Meaning                               | Engine                          |
| -------- | ------------------------------------- | ------------------------------- |
| m        | `^` and `$` match start/end of a line | PCRE2; `std::regex` since C++17 |
| i        | case insensitive matching             | all                             |
| s        | `.` matches every character           | PCRE2                           |

## Supported underlying engines

Depending on the underlying engine different RegEx features are supported. For more information check out the engine documentations.

- `std::regex` *default*
- PCRE2 *not supported*

```Bia
let engine_name = r"".name
```
