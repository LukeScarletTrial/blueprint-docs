# File System & I/O (`file_*`, `path_*`)

Blueprint includes a built-in, cross-platform file system API that works identically in interpreted mode and native standalone executables.

---

## Reading Files

### `file_read(path: string): string`
Reads the entire contents of a file into a UTF-8 string. Returns an empty string if the file does not exist or cannot be read.

```blueprint
@blueprint import Blueprint
Blueprint.Setup("ReaderApp", true)

func Main(): [
    def content = file_read("notes.txt")
    if str_len(content) > 0 [
        output("File content:")
        output(content)
    ] else [
        output("File is empty or not found.")
    ]
]
```

---

## Writing Files

### `file_write(path: string, data: string): bool`
Writes data to a file. Overwrites existing contents or creates the file if it does not exist. Returns `true` on success, `false` on failure.

```blueprint
@blueprint import Blueprint
Blueprint.Setup("WriterApp", true)

func Main(): [
    def success = file_write("output.log", "Build completed successfully.\n")
    if success [
        output("Log written!")
    ]
]
```

---

## Checking File Existence

### `file_exists(path: string): bool`
Returns `true` if a file exists at the given path.

```blueprint
if file_exists("config.bls") [
    output("Found project configuration.")
]
```

---

## Path Manipulation Utilities

Paths are handled cleanly across Windows (backslashes or slashes) and Linux/macOS (forward slashes).

### `path_join(a: string, b: string): string`
Joins two path fragments, ensuring a single path separator between them.

```blueprint
def full_path = path_join("assets", "sprites/hero.png")
// Result: "assets/sprites/hero.png"
```

### `path_ext(path: string): string`
Extracts the file extension without the leading dot. Returns an empty string if no extension is present.

```blueprint
def ext = path_ext("archive.tar.gz")
// Result: "gz"
```

### `path_filename(path: string): string`
Returns the file name portion of a path.

```blueprint
def name = path_filename("C:/Users/Documents/report.pdf")
// Result: "report.pdf"
```
