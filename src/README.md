# The Blueprint Programming Language

Welcome to the official documentation for **Blueprint** (`.bl`), a modern, high-performance programming language designed with clean syntax, static typing, and direct native compilation.

```blueprint
@blueprint import Blueprint
Blueprint.Setup("MyFirstApp", true)

func Main(): [
    def message = "Hello from Blueprint!"
    output(message)
]
```

## Why Blueprint?

- **Clean, Expressive Syntax**: Minimal punctuation and intuitive bracketed blocks `[...]`.
- **Direct Standalone Native Compilation**: Compiles directly to standalone native machine executables with zero VM or interpreter overhead.
- **Built-in Automatic Reference Counting (ARC)**: Deterministic, leak-free memory management for heap strings and dynamic objects without a garbage collection pause.
- **Rich Standard Library**: Built-in math, string manipulation, console IO, and zero-dependency 2D graphics windowing out of the box.
- **Printable Toolchain**: First-class package manager and build CLI (`printable`) with native project scaffolding and module resolution.
- **Modern IDE Integration**: Dedicated Visual Studio Code extension with dynamic AST autocompletion, hover documentation, snippets, and syntax highlighting.
