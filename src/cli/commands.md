# CLI Commands

The `printable` binary provides all CLI tooling for Blueprint.

## Commands Overview

| Command | Usage | Description |
| :--- | :--- | :--- |
| `printable init` | `printable init` | Scaffolds a new project with `config.bls` and `main.bl` |
| `printable module-init` | `printable module-init <name>` | Initializes a community module component structure |
| `printable compile-module` | `printable compile-module [dir]` | Compiles a module folder into a single portable `.blm` |
| `printable run` | `printable run [file.bl]` | Executes source code instantly via the developer runner |
| `printable build` | `printable build [file.bl]` | Compiles source directly into a standalone native `.exe` |
| `printable install` | `printable install <package>` | Downloads and installs a module into `./modules/` |

## `printable init`

Initializes a new Blueprint workspace:

```bash
printable init
```

## `printable module-init`

Creates a new modular component package ready for distribution or importing:

```bash
printable module-init my_library
```

This scaffolds:
- `my_library/package.bls`: package manifest and exported function list.
- `my_library/package.bl`: primary package file for exports and structures.
- `my_library/functions/`: directory of native component `.bl` function files.

## `printable compile-module`

Bundles and compiles a module folder into a single distribution module file (`.blm`):

```bash
printable compile-module my_library
# Produces my_library/my_library.blm
```

You can place `my_library.blm` directly into `./modules/` or distribute it as a single binary package!

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
