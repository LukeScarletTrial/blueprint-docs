# Automatic Reference Counting (ARC)

Blueprint manages memory through a deterministic **Automatic Reference Counting (ARC)** model for dynamic heap allocations.

## How ARC Works in Blueprint

1. **Deterministic Lifetime**: When a dynamic heap value (such as concatenated strings or heap structures) is allocated, its reference counter starts at `1`.
2. **Retain on Share**: Passing or assigning the reference increments the counter.
3. **Release on Scope Exit**: When a variable goes out of scope or is overwritten, its reference count is decremented.
4. **Immediate Deallocation**: As soon as the reference count reaches `0`, the memory is instantly freed. There are no stop-the-world garbage collection pauses.

## Value Semantics vs Reference Counting

- Value types (`int`, `bool`) are copied and stored directly on the stack or in CPU registers.
- Dynamic types (`string`, heap objects) use ARC headers:

```c
typedef struct {
    int32_t ref_count;
    size_t size;
} bl_arc_header_t;
```

This guarantees fast execution with predictable latency, making Blueprint suitable for games and real-time interactive applications.
