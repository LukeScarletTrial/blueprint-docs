# Project Configuration (`config.bls`)

The project configuration file (`config.bls` or `app.bls`) defines the package metadata, compiler options, and dependencies.

## Format Specification

`config.bls` is structured as JSON:

```json
{
  "name": "My Blueprint App",
  "version": "1.0.0",
  "author": "Developer",
  "entry": "main.bl",
  "dependencies": {
    "math_ext": "1.0.0"
  }
}
```

## Fields

- **`name`**: The human-readable name of your application or library.
- **`version`**: Semantic version string (e.g. `1.0.0`).
- **`author`**: Name or organization of the author.
- **`entry`**: The primary entry source file (defaults to `main.bl`).
- **`dependencies`**: Map of module names to versions or git repository URLs.
