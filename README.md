# 12d MTF Snippet Support

Language support for **12d Model MTF snippet files** (`.mtfsnippet`) in **Visual Studio Code**.

This is a **pure language extension**:
- No runtime code
- No telemetry
- No background processes
- No Language Server Protocol (LSP)

---

## Features

- Syntax highlighting for `.mtfsnippet` files
- Support for:
  - Line comments (`//`)
  - Block comments (`/* ... */`)
- Control-flow directives:
  - `@ if`, `@ else`, `@ end_if`
  - `@ repeat`, related conditional forms
- Token and macro highlighting:
  - `$()` variables
  - `$(_XXXX)` macro aliases
- Authoring snippets for:
  - Control-flow blocks
  - `@ def_tok` patterns
  - Insert and fixed modifier patterns

---

## File Association

This extension activates automatically for:

*.mtfsnippet

---

## Scope and Design

- **Language ID:** `12dmtfsnippet`
- **Grammar scope:** `source.12dmtfsnippet`
- Grammar- and snippet-only extension
- No validation, execution, or semantic analysis

---

## Intended Audience

Civil engineers and 12d Model users who author or maintain **MTF snippet libraries** and want reliable syntax highlighting and structured snippet authoring in VS Code.

---

## License

MIT
