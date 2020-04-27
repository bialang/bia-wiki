# String

## Comparing strings

Strings can be compared with the `==` or `!=` operators or with `equals` or `iequals` for case-insensitive comparing. Additionally `compare` or `icompare` return an integer value describing the comparison.

## Iterating over strings

When accessing characters at a specific position keep in mind that the code unit is returned and not the actual code point. When the string consists of only BMP characters all code units are also code points (see UTF-16 encoding).

```
let string = "aが"

// prints 3
print(string.length)

// prints a
print(string[0])

// prints the low surrogate and not が
print(string[1])
```

The correct way to iterate over strings:

```
for c in string {
	print(c)
}
```

The wrong way to iterate over string:

```
for string.length times {
	print(string[$i])
}
```

## Normal strings

'Normal' strings are enclosed in either two `"` (double quotes) or `'` (single quotes). Normal strings can expand over multiple lines.

## Raw strings

Raw strings cannot contain escape characters and can expand over mutliple lines.

## Template strings

Template strings are enclosed between two \` (grave accents). Inside these strings normal Bia expression can be evaluated inside `${}` and put inplace like following:

```
let x = 1
let z = 9

// prints y = x + z = 10
print(`y = x + z = ${x+z}`)
```

## Escape characters

The following escape sequences are valid if the string is not a [raw string](#raw-strings).

| Escape sequence | Meaning                               |
| --------------- | ------------------------------------- |
| \\|Backslash    |
| \'              | Single quote                          |
| \"              | Double quote                          |
| \a              | Audible bell                          |
| \b              | Backspace                             |
| \f              | Form feed (new page)                  |
| \n              | Line feed (new line)                  |
| \r              | Carriage return                       |
| \t              | Horizontal tab                        |
| \v              | Vertical tab                          |
| \nnn            | Arbitrary octal value                 |
| \xnn            | Arbitrary hexadecimal value           |
| \unnnn          | Arbitrary Unicode value (hexadecimal) |
| \Unnnnnnnn      | Arbitrary Unicode value (hexadecimal) |

## Guaranteed supported encodings

Depending on the underlying encoding implementation different encodings are supported.

Always supported:

- ASCII
- UTF-8
- UTF-16LE and UTF-16BE
- UTF-32LE and UTF-32BE

## Supported underlying libraries

- [ICU](#) *default*

If no library is provided only the guaranteed encodings [here](#guaranteed-supported-encodings) are supported.

## Internal implementation

Bia strings are stored as UTF-16 internally with the default CPU endianess. By defaut static strings are interned.

## Limitations

The maximum allowed string length cannot exceed 2^64-1 which is equal to `18 446 744 073 709 551 615`.