# Testing Blueprint Code (`printable test`)

Printable provides a built-in automated test runner capable of discovering and executing test suites across your project.

---

## Writing Tests

Test files follow standard naming conventions:
- Files ending in `_test.bl` (e.g. `math_test.bl`, `profile_test.bl`)
- Files starting with `test_` (e.g. `test_login.bl`)

### Example Test File (`math_test.bl`)

```blueprint
@blueprint import Blueprint
Blueprint.Setup("MathTests", true)

func TestAddition(): [
    def sum = 2 + 3
    if sum != 5 [
        output("Addition test failed!")
        process_exit(1)
    ]
]

func TestAbs(): [
    def val = math_abs(-42)
    if val != 42 [
        output("math_abs test failed!")
        process_exit(1)
    ]
]

func Main(): [
    TestAddition()
    TestAbs()
    output("All tests passed!")
]
```

---

## Running Tests

### Running All Project Tests
Simply execute:

```bash
printable test
```

Printable will recursively search your project directory (skipping `bin/`, `modules/`, and `target/`), execute each test in an isolated runner context, and report the results:

```text
Discovering and executing tests...

Running test 'tests/math_test.bl'... ✓ OK
Running test 'tests/strings_test.bl'... ✓ OK

Test Results: 2 passed, 0 failed, 2 total
```

### Running a Specific Test File
```bash
printable test tests/math_test.bl
```
