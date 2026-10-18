# Math Library

The Blueprint standard library includes high-performance integer math routines.

## Functions

### `math_abs(n: int): int`
Returns the absolute value of the integer:

```blueprint
output(math_abs(-42)) // Prints 42
```

### `math_pow(base: int, exp: int): int`
Calculates integer exponentiation (`base ^ exp`):

```blueprint
output(math_pow(2, 10)) // Prints 1024
```

### `math_min(a: int, b: int): int`
Returns the smaller of two integers:

```blueprint
output(math_min(15, 25)) // Prints 15
```

### `math_max(a: int, b: int): int`
Returns the larger of two integers:

```blueprint
output(math_max(15, 25)) // Prints 25
```
