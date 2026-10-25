# System, Environment & Time (`env_*`, `time_*`, `process_*`)

Blueprint provides native primitives for process execution, environment variables, timing, and lifecycle management.

---

## Environment Variables

### `env_get(key: string): string`
Fetches the string value of an environment variable. If the variable is unset, returns an empty string.

```blueprint
@blueprint import Blueprint
Blueprint.Setup("EnvApp", true)

func Main(): [
    def home = env_get("USERPROFILE")
    if str_len(home) == 0 [
        home = env_get("HOME")
    ]
    output("User Home: " + home)
]
```

### `env_set(key: string, value: string): bool`
Sets the value of an environment variable for the current process and its child processes. Returns `true` if successful.

```blueprint
def ok = env_set("BLUEPRINT_DEBUG", "1")
```

---

## Time Utilities

### `time_now(): int`
Returns the current UTC Unix timestamp in seconds (seconds elapsed since `January 1, 1970 00:00:00 UTC`).

```blueprint
def start_time = time_now()
// Perform long running operations...
def end_time = time_now()
def elapsed = end_time - start_time
output("Elapsed seconds: " + elapsed)
```

### `time_sleep(ms: int): void`
Suspends thread execution for the specified number of milliseconds.

```blueprint
output("Waiting 2 seconds...")
time_sleep(2000)
output("Resumed!")
```

---

## Process Lifecycle

### `process_exit(code: int): void`
Exits the process immediately with the specified integer status code (`0` for success, non-zero for errors).

```blueprint
if !file_exists("required.dat") [
    output("Error: missing data file")
    process_exit(1)
]
```
