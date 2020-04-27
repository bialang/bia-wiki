# Op Codes

- [Parameter types](#parameter-types)
	- [Constant](#constant)
	- [Member Source](#member-source)
	- [Member Destination](#member-destination)
- [Variantions](#variantions)
	- [8 Bit Variants](#8-bit-variants)
	- [4 Bit Variants](#4-bit-variants)
	- [2 Bit Variants](#2-bit-variants)
	- [0 Bit Variants](#0-bit-variants)

## Parameter types

### Constant

| Name   | Description             | Parameter Size | Value |
| ------ | ----------------------- | -------------- | ----- |
| int8   | Signed int              | 8 bit          | `0`   |
| int16  | Signed int              | 16 bit         | `1`   |
| int32  | Signed int              | 32 bit         | `2`   |
| double | IEEE 754 floating point | 64 bit         | `3`   |

### Member Source

| Name       | Description                                       | Parameter Size | Value |
| ---------- | ------------------------------------------------- | -------------- | ----- |
| tos        | Get top of stack                                  | 0 bit          | `0`   |
| args       | Get member with unsigned offset from arg position | 8 bit          | `1`   |
| global16   |
| local16    |
| resource16 |
| global8    |
| local8     |
| resource8  |

### Member Destination

| Name     | Description          | Parameter Size | Value |
| -------- | -------------------- | -------------- | ----- |
| tos      | Push on top of stack | 0 bit          | `0`   |
| global16 |
| local16  |
| global8  |
| local8   |

## Variantions

### 8 Bit Variants

| Op Code     | 1. Parameter          | 2. Parameter       | 3. Parameter       |
| ----------- | --------------------- | ------------------ | ------------------ |
| instantiate | constant              | member destination | *n/a*              |
| invoke      | uint8 parameter count | member source      | member destination |
| refer       | member source         | member destination | *n/a*              |
| copy        | member source         | member destination | *n/a*              |

### 4 Bit Variants

| Op Code     | 1. Parameter          | 2. Parameter  |
| ----------- | --------------------- | ------------- |
| invoke_void | uint8 parameter count | member source |
| test        | member source         | *n/a*         |

### 2 Bit Variants

| Op Code    | 1. Parameter |
| ---------- | ------------ |
| jump       | offset       |
| jump_true  | offset       |
| jump_false | offset       |

### 0 Bit Variants

| Op Code     |
| ----------- |
| return_void |
| test_top    |
