# C Foreign Function Interface (FFI)

Blueprint provides native C interoperability through its first-class Foreign Function Interface. This allows Blueprint code to call existing C libraries and system APIs directly without wrapping them in shell scripts or interpreting C strings dynamically.

## Importing C Support

To enable C interoperability in your Blueprint source file, import the C namespace:

```blueprint
@blueprint import Blueprint
@blueprint import C
Blueprint.Setup("FFI Example", true)
```

## Directives

### 1. `C.Include("<header>")`
Instructs the compiler to emit a `#include` directive for the specified C system or local header:

```blueprint
C.Include("math.h")
C.Include("stdio.h")
```

### 2. `C.Link("<library>")`
Instructs the native linker to link against the specified library (equivalent to `-l<library>` in GCC/Clang):

```blueprint
C.Link("m")
C.Link("pthread")
```

### 3. `C.Extern("<signature>")`
Declares an external C function signature so Blueprint's parser and semantic analyzer recognize it and generate the proper native function prototype:

```blueprint
C.Extern("double sqrt(double x)")
C.Extern("double pow(double base, double exponent)")
```

## Example: Calling C Standard Math Library

```blueprint
@blueprint import Blueprint
@blueprint import C
Blueprint.Setup("Math FFI Example", true)

C.Include("math.h")
C.Link("m")
C.Extern("double sqrt(double x)")

func Main(): [
    def val = sqrt(49.0)
    output("Square root of 49.0 is: " + val)
]
```

When compiled with `printable build` or the Blueprint compiler, this produces a standalone native binary directly linked with GCC/Clang and `libm`.
