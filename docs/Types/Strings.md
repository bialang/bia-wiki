# String

## Comparing Strings

Strings can be compared with the `==` or `!=` operators or with `equals` or `iequals` for case-insensitive comparing. Additionally `compare` or `icompare` return an integer value describing the comparison.

```bia
import io

io.print("bia" == "Bia") // 0
io.print("bia" != "Bia") // 1
io.print("Bia" in "I like Bia") // 1
```

## Members

- `length` the length of the strings (number of bytes not code points)
- `lower()` returns a copy of this string in lowercase
- `upper()` returns a copy of this string in uppercase

## Iterating over Strings

!!! warning "This section is out of date"

When accessing characters at a specific position keep in mind that the code unit is returned and not the actual code point. When the string consists of only BMP characters all code units are also code points (see UTF-16 encoding).

```bia
let string = "aが"

// prints 3
print(string.length)
```

## Escape Characters

| Escape sequence | Meaning              |
| --------------- | -------------------- |
| \\|Backslash    |                      |
| \"              | Double quote         |
| \a              | Audible bell         |
| \b              | Backspace            |
| \f              | Form feed (new page) |
| \n              | Line feed (new line) |
| \r              | Carriage return      |
| \t              | Horizontal tab       |
| \v              | Vertical tab         |

## Guaranteed supported Encodings

Depending on the underlying encoding implementation different encodings are supported.

Always supported:

- ASCII
- UTF-8
- UTF-16LE and UTF-16BE
- UTF-32LE and UTF-32BE

## Internal Storage

Bia strings are stored as UTF-8 internally.
