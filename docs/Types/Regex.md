# Native Regular Expressions

## Syntax

The pattern must be wrapped between `/` like following:

```bia
let pattern = /ab+/
```

A `/` can be escaped with a `\`. The `\` only acts as a escape character in that perticular case.

!!! note
    `//` is not a valid regex expression. See [comments](../Syntax/Comments.md) for more information.

## Modifiers[^1]

Modifiers come immediately after the enclosing `/` like:

```bia
let pattern = /a.+/si
```

| Modifier | Meaning                               | Engine                          |
| -------- | ------------------------------------- | ------------------------------- |
| m        | `^` and `$` match start/end of a line | PCRE2; `std::regex` since C++17 |
| i        | case insensitive matching             | all                             |
| s        | `.` matches every character           | PCRE2                           |

## Supported underlying engines

Depending on the underlying engine different RegEx features are supported. For more information check out the engine documentations.

- `std::regex` *default*
- PCRE2[^1]

```bia
let engine_name = /./.name
```

[^1]: This feature has not been implemented yet.
