# Control Flow (`if` / `else`)

Conditional logic is expressed through `if` and `else` blocks. Parentheses around conditions are optional.

## `if` Statements

```blueprint
if age >= 18 [
    output("Adult Access Granted")
]
```

## `if` / `else` Statements

```blueprint
if score >= 90 [
    output("Grade: A")
] else [
    output("Grade: Pass")
]
```

## Nested Conditionals

```blueprint
if is_connected [
    if has_auth [
        output("Welcome back!")
    ] else [
        output("Please log in.")
    ]
]
```
