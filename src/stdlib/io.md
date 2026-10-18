# Input / Output (`output`, `input`)

The Blueprint standard library includes built-in functions for console interaction.

## `output(val)`

Prints any printable value (string, integer, boolean) to the standard output followed by a newline:

```blueprint
output("Hello, Blueprint!")
output(42)
output(true)
```

## `input(prompt)`

Displays an optional prompt message and reads a full line of text from `stdin`, returning a `string`:

```blueprint
def name = input("Enter your name: ")
output("Welcome, " + name + "!")
```
