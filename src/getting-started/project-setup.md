# Creating a Project

Every Blueprint application is organized as a workspace with a configuration manifest (`config.bls` or `app.bls`) and source files (`.bl`).

## Initializing a New Workspace

Run the `init` command in your project directory:

```bash
mkdir MyGame
cd MyGame
printable init
```

This generates two essential files:

1. `config.bls`: The JSON project descriptor.
2. `main.bl`: The main entry-point source file.

### Directory Layout

```text
MyGame/
├── config.bls       # Application metadata and dependency definitions
├── main.bl          # Main entry file containing Main()
├── modules/         # Downloaded third-party Blueprint packages
└── bin/             # Native compiled binary outputs (created on build)
```
