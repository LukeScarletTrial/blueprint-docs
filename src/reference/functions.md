# Functions & Parameters

Functions are declared with the `func` keyword.

## Basic Syntax

```blueprint
func Add(a: int, b: int): int [
    return a + b
]
```

If a return type is omitted, it defaults to `void`:

```blueprint
func LogMessage(msg: string): [
    output(msg)
]
```

Parameters may also omit explicit types, in which case they are inferred from usage:

```blueprint
func Double(val): [
    return val * 2
]
```

## Return Statements

Functions return values using the `return` statement:

```blueprint
func MaxValue(x: int, y: int): int [
    if x > y [
        return x
    ]
    return y
]
```
