# Op Codes
## Memory Address
A memory references a location on the stack. The value is an absolute offset from the start of the last stack frame.

## Operations
### Store Operation
This operation stores an immediate value inside the specified location.

```
store <size> <destination>, <immediate>
```

### Copy Operation
This operation copies the value of the source location to the destination location.

```
copy <size> <destination>, <source>
```

### Branch Operations
```
op <offset>
```

#### Arguments
##### Available Operations
- `jmp`: An unconditional jump.
- `jmp_false`: Jumps if the test register is equal to `0`.
- `jmp_true`: Jumps if the test register is not equal to `0`.

##### Offset
The offset is relative to the end of the branch instruction in bytes.

### With 2 Operands
```
op <size> <op1>, <op2>
```

#### Arguments
##### Available Operations
- `add`, `fadd`
- `sub`, `fsub`
- `mul`, `fmul`
- `sdiv`, `udiv`, `fdiv`
- `srem`, `urem`, `frem`: Remainder.
- `and`, `or`, `xor`: Bitwise operations.
- `eq`, `neq`, `lt`, `leq`, `gt`, `geq`: All standard comparison functions that yield a boolean. The final result is stored inside the test register.

##### Available Sizes
- `8`, `16`, `32`, `64`

##### First Operand
*op1* must be a memory address. The result of the operation is store here if not specified otherwise.

##### Second Operand
*op2* must be either a memory address or an immediate.

## Examples
The following examples demonstrate the use of the op codes. The actual compiler may optimize the code.

In Bia:

```bia
let x = 0
let y = x + 0
let z = 1 + y
```

```
store 32 x, 0

cp 32 y, x
add 32 y, 0

store 32 z, 1
add 32 z, y
```
