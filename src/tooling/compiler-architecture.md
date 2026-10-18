# Native Compiler Architecture

Blueprint is designed for direct compilation to native CPU instructions with zero runtime virtual machines.

## Architecture Stages

```text
Source Code (.bl)
       │
       ▼
  1. Lexer (Logos Tokenizer)
       │
       ▼
  2. Parser (Chumsky AST Builder)
       │
       ▼
  3. Semantic Analyzer (Type-checking, symbol resolution, scoping)
       │
       ▼
  4. Code Generator (Direct Native Assembly / Machine Code)
       │
       ▼
Native Executable (.exe / ELF)
```

## Compilation Phases

1. **Tokenization (`lexer.rs`)**: High-speed lexical analysis transforming UTF-8 source into structured token streams with exact source spans.
2. **Parsing (`parser.rs`)**: Combinator-based recursive descent parser validating syntax and producing the abstract syntax tree (`Program`).
3. **Semantic Checking (`semantics.rs`)**:
   - Type inference and strict validation
   - Struct field resolution and duplicate check
   - Scope-aware variable resolution
   - Function signature and call arity verification
4. **Code Generation (`codegen.rs`)**: Emits optimized native code, linking system libraries (`user32`, `gdi32`, `libm`) for direct execution.
