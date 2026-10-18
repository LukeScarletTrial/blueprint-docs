# Structures (`defstruct`)

Custom composite data types are defined with the `defstruct` keyword.

## Defining a Struct

```blueprint
defstruct Player [
    name: string,
    score: int,
    is_alive: bool
]
```

## Instantiating a Struct

Structs can be constructed using positional syntax:

```blueprint
def p1 = Player["Hero", 1500, true]
```

Or using named field syntax:

```blueprint
def p2 = Player{ name: "Mage", score: 2300, is_alive: true }
```

## Accessing Fields

Fields are accessed using dot notation:

```blueprint
output(p1.name)
if p1.is_alive [
    output(p1.score)
]
```
