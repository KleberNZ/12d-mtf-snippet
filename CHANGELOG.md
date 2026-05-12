# Changelog

All notable changes to the **12d MTF Snippet Support** extension are documented here.

## [0.1.8] - 2026-05-12

### Added
- Added highlighting for snippet parameter regions.
- Added highlighting for multiline snippet parameter blocks.
- Added highlighting for `OPEN` / `CLOSED` region states.
- Preserved normal `//` comments.

## [0.1.7] – 2026-01-22

- Fixed syntax highlighting for @ def_tok_no_concat and def_tok_* directives

## [0.1.6] – 2026-01-22

### Added
- Regex-based code folding for MTF control-flow blocks:
  - `@ if* … @ end_if`
  - `@ repeat … @ end_repeat`
- Folding is no longer indentation-dependent.

### Notes
- `@ else` is intentionally not a fold boundary due to VS Code language-only limitations.

## [0.1.5] - 2026-01-21

### Fixed
- Marketplace screenshots not rendering due to packaging issue

## [0.1.4] - 2026-01-21

### Changed
- Restored screenshots in README and Marketplace Overview

## [0.1.3] - 2026-01-21

### Changed
- Updated Marketplace Overview and README for clarity and completeness
- Documented full snippet coverage based on 12d Model Manual Section 19.7

## [0.1.2] - 2026-01-21

### Added
- Complete set of MTF authoring snippets based on **12d Model Manual – Section 19.7**
- Full coverage of documented MTF commands and patterns available in the manual
- Expanded `mtf.code-snippets` to reflect official 12d syntax and structure

### Changed
- README updated to reflect full manual coverage and intended authoring workflow

## [0.1.1] - 2026-01-19

### Changed
- Improved README clarity and structure
- Added syntax highlighting and snippet IntelliSense screenshots


## [0.1.0] – 2026-01-18

### Added
- Initial public release
- Syntax highlighting for `.mtfsnippet` files
- Support for comments, control-flow directives, tokens, and macros
- Authoring snippets for control flow, `@ def_tok`, insert and fixed modifier patterns
