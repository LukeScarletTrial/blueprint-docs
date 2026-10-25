# Blueprint Modules (`.blm`) & Binary Packages

Blueprint supports distributing reusable packages either as component directories or as single portable precompiled binary modules using the **`.blm`** format (**B**lueprint **L**ibrary **M**odule).

---

## What is a `.blm` File?

A `.blm` file is a compiled, self-contained single-file module that acts like a pre-packaged library binary for Blueprint. It bundles:
1. Package metadata and version info from `package.bls`
2. Declarations and types from `package.bl`
3. All component function implementations from `functions/*.bl`

Instead of distributing a complex directory tree with dozens of loose files, you compile your package into `<modulename>.blm` and distribute it as a single file.

---

## Module Directory Structure vs `.blm`

When authoring a module locally:

```text
my_library/
├── package.bls        # Manifest (name, version, exported functions)
├── package.bl         # Struct definitions and module exports
└── functions/         # Individual function files
    ├── add.bl
    └── multiply.bl
```

Compiling it with Printable:

```bash
printable compile-module my_library
```

Produces:

```text
my_library/my_library.blm
```

---

## Importing `.blm` in Your Applications

Once compiled, place the `.blm` file directly into your application's `modules/` folder or project root:

```text
my_app/
├── config.bls
├── main.bl
└── modules/
    └── my_library.blm
```

Import and call it directly in your Blueprint code:

```blueprint
@blueprint import Blueprint
@blueprint import modules/my_library

Blueprint.Setup("MyApp", true)

func Main(): [
    def sum = my_library.add(10, 20)
    output("Sum: " + sum)
]
```

---

## Compiling Modules with Printable

### From Inside a Module Folder:
```bash
cd my_library
printable compile-module .
# Automatically detects package name from package.bls and produces my_library.blm
```

### From Parent Directory:
```bash
printable compile-module ./my_library
# Produces my_library/my_library.blm
```

### Specifying a Custom Output Path:
```bash
printable compile-module ./my_library ../another_project/modules/my_library.blm
```
