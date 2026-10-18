# Syntax & Structure

Blueprint syntax is designed to be clean, readable, and free of redundant semicolons.

## Comments

Single-line comments start with `//` and continue to the end of the line:

```blueprint
// This is a single-line comment
def x = 10 // Inline comment
```

## Blocks

Code blocks in Blueprint are enclosed in square brackets `[` and `]`:

```blueprint
func Example(): [
    // function body
    if condition [
        // nested block
    ]
]
```

## Keywords

The reserved keywords in Blueprint are:

- `def` — Declares a variable
- `func` — Declares a function
- `defstruct` — Declares a custom composite data structure
- `return` — Returns from a function
- `if` / `else` — Branching statements
- `true` / `false` — Boolean literal constants
- `import` — Module importing
