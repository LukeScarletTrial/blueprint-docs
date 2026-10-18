# String Manipulation

Strings in Blueprint are UTF-8 encoded text sequences managed via ARC.

## Concatenation (`+`)

Strings can be concatenated using the `+` operator:

```blueprint
def first = "Game"
def second = "Engine"
def title = first + " " + second
output(title) // Prints "Game Engine"
```

## `str_len(s)`

Returns the integer length of a string in bytes/characters:

```blueprint
def text = "Blueprint"
def len = str_len(text)
output(len) // Prints 9
```
