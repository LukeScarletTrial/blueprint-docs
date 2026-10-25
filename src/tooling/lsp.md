# Language Server Protocol (`blueprint-lsp`)

The **Blueprint Language Server** (`blueprint-lsp`) implements the standard Language Server Protocol (LSP) over JSON-RPC, enabling IDEs and code editors (such as VS Code, Neovim, Emacs, and Sublime Text) to offer real-time language intelligence.

---

## Capabilities Provided

1. **Live Diagnostics**:
   - Compiles source buffers on the fly upon open (`textDocument/didOpen`) and change (`textDocument/didChange`).
   - Surfaces syntax errors, missing `Blueprint.Setup()` declarations, undefined variables, and type mismatches with exact line and column ranges.

2. **Smart Autocompletion**:
   - Triggers on `.`, `@`, and `:` characters.
   - Suggests keywords, built-in standard library functions (`math_*`, `str_*`, `file_*`, `env_*`, `time_*`), and type identifiers (`i8`–`i64`, `u8`–`u64`, `f32`, `f64`).

3. **Symbol Hover Documentation**:
   - Displays markdown-formatted tooltips showing function signatures and entity details.

---

## Running the LSP Server Standalone

The server communicates via standard I/O and Content-Length framed JSON-RPC packets:

```bash
blueprint-lsp
```

It is installed in your system PATH (`~/.cargo/bin/blueprint-lsp.exe` or `/usr/local/bin/blueprint-lsp`).

---

## Editor Configuration Example (Neovim / nvim-lspconfig)

```lua
local lspconfig = require('lspconfig')
local configs = require('lspconfig.configs')

if not configs.blueprint_lsp then
  configs.blueprint_lsp = {
    default_config = {
      cmd = { 'blueprint-lsp' },
      filetypes = { 'blueprint' },
      root_dir = lspconfig.util.root_pattern('config.bls', 'app.bls', '.git'),
    },
  }
end

lspconfig.blueprint_lsp.setup({})
```
