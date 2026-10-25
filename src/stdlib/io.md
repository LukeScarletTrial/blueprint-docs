# Input / Output (`output`, `input`)

The Blueprint standard library includes built-in functions for console interaction.

## `output(val)`

Prints any printable value (string, integer, boolean) to the standard output followed by a newline:

```blueprint
output("Hello, Blueprint!")
output(42)
output(true)
```

## `input(prompt)`

Displays an optional prompt message and reads a full line of text from `stdin`, returning a `string`:

```blueprint
def name = input("Enter your name: ")
output("Welcome, " + name + "!")
```

## File I/O Operations

Blueprint provides standard file system functions:

### `file_read(path: string): string`
Reads the entire contents of a file as a string. Returns an empty string if the file cannot be opened.

```blueprint
def content = file_read("config.json")
output(content)
```

### `file_write(path: string, data: string): bool`
Writes text contents into a destination file path. Returns `true` on success, `false` otherwise.

```blueprint
def ok = file_write("output.txt", "Log entry: OK\n")
```

### `file_exists(path: string): bool`
Checks whether a given file exists on the filesystem.

```blueprint
if file_exists("data.bin") [
    output("File is present.")
]
```

## Path Utilities

### `path_join(a: string, b: string): string`
Joins two path segments using the system separator.

### `path_ext(p: string): string`
Returns the extension of the given path without the leading dot.

### `path_filename(p: string): string`
Returns the final file name component of the given path.

## Environment & Process Control

### `env_get(key: string): string`
Reads the value of an environment variable. Returns an empty string if unset.

### `env_set(key: string, value: string): bool`
Sets the value of an environment variable for the current process.

### `process_exit(code: int): void`
Terminates the application immediately with the given exit status code.

### `time_now(): int`
Returns the current UTC Unix timestamp in seconds.

### `time_sleep(ms: int): void`
Suspends execution of the current thread for the specified number of milliseconds.
