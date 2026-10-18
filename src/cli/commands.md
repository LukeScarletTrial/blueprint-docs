# CLI Commands

The `printable` binary provides all CLI tooling for Blueprint.

## Commands Overview

| Command | Usage | Description |
| :--- | :--- | :--- |
| `printable init` | `printable init [name]` | Scaffolds a new project with `config.bls` and `main.bl` |
| `printable run` | `printable run [file.bl]` | Executes source code instantly via the developer runner |
| `printable build` | `printable build [file.bl]` | Compiles source directly into a standalone native `.exe` |
| `printable install` | `printable install <package>` | Downloads and installs a module into `./modules/` |

## `printable init`

Initializes a new Blueprint workspace:

```bash
printable init
```

## `printable run`

Runs the default entry file (`main.bl`) or a specific script:

```bash
printable run
printable run ./examples/game.bl
```

## `printable build`

Compiles the program into an optimized executable under `bin/`:

```bash
printable build
# Output produced at bin/main.exe
```

## `printable install`

Resolves third-party packages or Git dependencies into `./modules/`:

```bash
printable install https://github.com/LukeScarletTrial/blueprint-sprites.git
```
