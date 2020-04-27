# Regex

## Syntax

The pattern must be wrapped between `/` like following:

```
let pattern = /ab+/
```

## Modifiers

Modifiers come immediately after the enclosing `/` like:

```
let pattern = /a.+/si
```

| Modifier | Meaning                               |
| -------- | ------------------------------------- |
| m        | `^` and `$` match start/end of a line |
| i        | case insensitive matching             |
| s        | `.` matches every character           |

## Supported underlying engines

Depending on the underlying engine different RegEx features are supported. For more information check out the engine documentations.

- [PCRE2](#) *default*
- [boost:regex](#)
- [std::regex](#)

If no engine is selected, the feature will be disabled and `bia::exception::unsupported_feature_exception` will be thrown when used. The underlying engine can be check with:

```
// returns null if no engine is supported
let engine = //.name()
```