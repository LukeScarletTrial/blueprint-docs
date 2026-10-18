# VS Code Extension & Autocomplete

The official **Blueprint Language Extension** for Visual Studio Code provides full IDE intelligence.

## Features

- **TextMate Syntax Grammar**: Clean, accurate syntax highlighting for `.bl` source files, `.bls` setup files, and `.blm` compiled module files.
- **Dedicated Language Icons**:
  - Blueprint `.bl` source files (`logo.png`)
  - Blueprint `.bls` config files (`deps_logo.png`)
  - Blueprint `.blm` compiled modules (`blm_logo.png`)
- **Dynamic AST Autocompleter**:
  - Automatically indexes all functions, structs, and variables across your project and imported `.blm` modules.
  - Generates function call snippets with tab stops for each parameter: `MyFunc(${1:param1}, ${2:param2})`.
  - Automatically completes `defstruct` initializers with all fields pre-populated.
  - Provides snippets for control structures (`if`, `ifelse`, `func`, `defstruct`).
  - Autocompletes standard library math, string, IO, and graphics functions with full parameter signatures.

## Installing the Extension

Install the packaged `.vsix` file:

```bash
code --install-extension blueprint-lang-0.1.1.vsix
```
