# Installation & Toolchain

The Blueprint toolchain consists of the compiler (`blueprint_compiler`), the official CLI and package manager (`printable`), and the Visual Studio Code extension.

## Requirements

- **Operating System**: Windows 10/11, Linux, or macOS.
- **C/Native Toolchain**: MinGW-w64 GCC or Clang (available via MSYS2 or system package manager).
- **Rust Toolchain** *(Optional, only if building the compiler from source)*: Rust 1.75+.

## Installing Printable

Printable is the single binary command-line manager for Blueprint.

### Building from Source

```bash
git clone https://github.com/LukeScarletTrial/printable.git
cd printable
cargo build --release
```

Copy the generated binary `target/release/printable.exe` into your system `PATH` (for example, `%USERPROFILE%\.cargo\bin` or `/usr/local/bin`).

Verify the installation:

```bash
printable --help
```

## Installing the VS Code Extension

1. Clone or open the `vscode` directory from the [Blueprint repository](https://github.com/LukeScarletTrial/blueprint).
2. Install the `.vsix` package:

```bash
code --install-extension blueprint-lang-0.1.0.vsix
```

This immediately registers syntax coloring and dynamic autocompletion for all `.bl` files.
