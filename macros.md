# LLL macros

Since LLL is written as S-expressions it also took design cues from Lisp and thus defines a limited set of native macros and some builtin macros. There different implementations supported a different subset of them.

## Specials

#### `lll` (2 args)

*Supported by: Solidity, Serpent, Viper*

#### `lll` (3 args)

*Supported by: Solidity*

#### `asm`

*Supported by: Solidity*

Raw EVM assembly instructions follow.

```
(asm MUL DIV POP)
```

#### `include`

*Supported by: Solidity*

Include another LLL source file.

```
(include ./otherfile.lll)
```

#### `set`

*Supported by: Solidity, Serpent, Viper*

#### `get`

*Supported by: Solidity*


#### `ref`

*Supported by: Solidity*


#### `def`

*Supported by: Solidity*


#### `lit`

*Supported by: Solidity*


#### `alloc`

*Supported by: Solidity*


#### `seq`

*Supported by: Solidity, Viper*


#### `raw`

*Supported by: Solidity*


#### `bytecodesize`

*Supported by: Solidity*

#### `comment`

*Supported by: Serpent*

#### `ops`

*Supported by: Serpent*

#### `with`

*Supported by: Serpent, Viper*

## Arithmetic operators

#### `+`

*Supported by: Solidity*

Addition of two arguments.

```
(+ 1 2)
```

#### `-`

*Supported by: Solidity*

Subtraction of two arguments.

```
(- 1 2)
```

#### `*`

*Supported by: Solidity*

Multiplication of two arguments.

```
(* 1 2)
```

#### `/`

*Supported by: Solidity*

Unsigned division of two arguments.

```
(/ 2 1)
```

#### `%`

*Supported by: Solidity*

Modulo of two arguments.

```
(% 2 2)
```

## Comparison operators

#### `=`

*Supported by: Solidity*

Equal to.

```
(= 1 1)
```

#### `!=`

*Supported by: Solidity*

Not equal to.

```
(!= 1 2)
```

#### `<`

*Supported by: Solidity*

Unsigned less than.

#### `<=`

*Supported by: Solidity*

Unsigned less than or equal to.

#### `>`

*Supported by: Solidity*

Unsigned greater than.

#### `>=`

*Supported by: Solidity*

Unsigned greater than or equal to.

#### `S<`

*Supported by: Solidity*

Signed less than.

#### `S<=`

*Supported by: Solidity*

Signed less than or equal to.

#### `S>`

*Supported by: Solidity*

Signed greater than.

#### `S>=`

*Supported by: Solidity*

Signed greater than or equal to.

## Bitwise operators

#### `~`

*Supported by: Solidity*

Bitwise `NOT` of one argument.

```
(~ 1)
```

#### `&`

*Supported by: Solidity*

Bitwise `AND` of two arguments

```
(& 1 2)
```

#### `|`

*Supported by: Solidity*

Bitwise `OR` of two arguments.

```
(| 1 2)
```

#### `^`

*Supported by: Solidity*

Bitwise `XOR` of two arguments.

```
(^ 1 2)
```

## Logical operators

#### `!`

*Supported by: Solidity*

Logical negation of one argument.

```
(! 1)
```

#### `&&` (min 1 arg(s))

*Supported by: Solidity*

Logical `AND` of two arguments.

```
(&& 1 2)
```

#### `||` (min 1 arg(s))

*Supported by: Solidity*

Logical `OR` of two arguments.

```
(&& 1 2)
```

## Control flow

#### `if` (2 args)

*Supported by: Solidity, Viper*

#### `if` (3 args)

*Supported by: Solidity, Viper*

#### `when`

*Supported by: Solidity*

#### `unless`

*Supported by: Solidity*

#### `while`

*Supported by: Solidity*

#### `until`

*Supported by: Solidity*

#### `for`

*Supported by: Solidity*


## EVM instructions

TBA all EVM instructions supported (Solidity, Serpent, Viper differ here a bit)


## Solidity specific

#### `panic`

Insert an `INVALID` opcode.

#### `shl`

Logical shift left.

```
(shl 65536 8)
```

#### `shr`

Logical shift right.

```
(shr 65536 8)
```

#### `return`

Return a value.

```
(return 1)
```

#### `returnlll`

Take expressions and return a compiled bytecode.

```
(returnlll (seq (return 1)))
```

#### `allgas`

#### `send` (2 args)

#### `send` (3 args)

#### `msg` (6 args)

#### `msg` (5 args)

#### `msg` (4 args)

#### `msg` (3 args)

#### `msg` (2 args)

#### `create` (2 args)

#### `create` (1 arg)

#### `sha3` (2 args)

#### `sha3` (1 arg)

#### `sha3pair` (2 args)

#### `sha3trip` (3 args)

#### `makeperm`

#### `permcount`

#### `perm`

#### `ecrecover`

#### `sha256` (2 args)

#### `sha256` (1 arg)

#### `ripemd160` (2 args)

#### `ripemd160` (1 arg)

#### `wei`

#### `szabo`

#### `finney`

#### `ether`


## Viper specific

#### `repeat` (4 args)

Repeat (for loops) statements.

```
(repeat memloc, start, rounds, body)
```

#### `pass` (0 args)

Pass statement, does nothing.

#### `break` (0 args)

Break from inside a `repeat` statement.

#### `assert` (1 arg)

Uses the `revert` opcode if the expression is false.

#### `codelen`

The length of the code.

#### `codeload`

`CALLDATALOAD` equivalent for code.

#### `uclamplt` (2 args)

Unsigned less than statement.

#### `uclample` (2 args)

Unsigned less than or equal statement.

#### `clamplt` (2 args)

Signed less than statement.

#### `clample` (2 args)

Signed less than or equal statement.

#### `uclampgt` (2 args)

Unsigned greater than statement.

#### `uclampge` (2 args)

Unsigned greater than or equal statement.

#### `clampgt` (2 args)

Signed greater than statement.

#### `clampge` (2 args)

Signed greater than or equal statement.

#### `clamp` (3 args)

Signed clamp, check against upper and lower bounds.

#### `uclamp` (3 args)

Unsigned clamp, check against upper and lower bounds.

#### `clamp_nonzero` (1 args)

Checks that arg isn't zero.

#### `sha3_32` (1 args)

SHA3 a single value.

#### `le` (2 args)

Unsigned less than statement.

#### `ge` (2 args)

Unsigned greater than statement.

#### `sle` (2 args)

Signed less than statement.

#### `sge` (2 args)

Signed greater than statement.

#### `ne` (2 args)

Checks for inequality.

#### `ceil32` (1 args)

Rounds up to the nearest factor of 32.
