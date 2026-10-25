# Variables & Types

Blueprint is statically typed with strong type inference.

## Declaring Variables

Variables are introduced using the `def` keyword:

```blueprint
def message = "Hello"
def count = 42
def active = true
```

### Explicit Type Annotations

You can optionally specify the variable type using a colon `: Type`:

```blueprint
def user_id: int = 1001
def username: string = "Luke"
def is_admin: bool = false
```

## Primitive Types

| Type | Description | Example |
| :--- | :--- | :--- |
| `int` / `i64` | 64-bit signed integer | `12`, `-45`, `0` |
| `i8` | 8-bit signed integer | `127`, `-128` |
| `i16` | 16-bit signed integer | `32767`, `-32768` |
| `i32` | 32-bit signed integer | `2147483647` |
| `u8` | 8-bit unsigned integer | `0`, `255` |
| `u16` | 16-bit unsigned integer | `0`, `65535` |
| `u32` | 32-bit unsigned integer | `0`, `4294967295` |
| `u64` | 64-bit unsigned integer | `0`, `18446744073709551615` |
| `f32` | 32-bit IEEE 754 single-precision float | `3.14`, `-0.5` |
| `f64` / `float` | 64-bit IEEE 754 double-precision float | `2.718281828459` |
| `bool` | Boolean truth value | `true`, `false` |
| `string` / `str` | UTF-8 encoded text string | `"Blueprint"`, `"Line\n"` |
| `void` | Empty/unit return type | `void` |
| Custom | User-defined structs (`defstruct`) | `Profile`, `Point2D` |
