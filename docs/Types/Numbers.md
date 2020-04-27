# Numbers

## Integers

Integers can be of arbitrary length if Bia was built with a supported big int library, otherwise the integers range from `-2^63` to `2^63-1`.

## Floating points

Floating point values are stored in a IEEE 754 double precision encoding. The internal encoding is platform specific.

## Integer literals

The following literals can percede an integer digit and change the base of the number. If no literal is given, the decimal base is assumed.

| Literal    | Base        |
| ---------- | ----------- |
| 0x *or* 0X | Hexadecimal |
| 0b *or* 0B | Binary      |
| 0          | Ocatal      |