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
| `int` | 64-bit signed integer | `12`, `-45`, `0` |
| `bool` | Boolean truth value | `true`, `false` |
| `string` / `str` | UTF-8 encoded text string | `"Blueprint"`, `"Line\n"` |
| `void` | Empty/unit return type | `void` |
| Custom | User-defined structs (`defstruct`) | `Profile`, `Point2D` |
