## Repository Purpose

This repository contains the VS Code extension `12d-mtf-snippet`.

Marketplace name:

* `12d MTF Snippet Support`

The extension provides language support for 12d Model `.mtfsnippet` files, including:

* Syntax highlighting
* Code snippets
* Language configuration

This is currently a lightweight/declarative VS Code extension. Do not add runtime TypeScript or JavaScript activation code unless explicitly requested.

## Important Files

### `package.json`

Defines the VS Code extension manifest, including:

* Extension metadata
* Language contribution
* Grammar contribution
* Snippet contribution
* Commands/scripts for packaging and validation

Use care when editing this file. Changes can affect how VS Code recognises the language, grammar, snippets, and Marketplace package.

### `syntaxes/12dmtfsnippet.tmLanguage.json`

TextMate grammar used for syntax highlighting of `.mtfsnippet` files.

Grammar changes should be targeted, minimal, and tested against real `.mtfsnippet` examples.

### `snippets/mtf.code-snippets`

Contains VS Code snippets for `.mtfsnippet` files.

Snippet changes should use clear prefixes, useful descriptions, and valid snippet body syntax.

### `language-configuration.json`

Defines editor behaviour such as comments, brackets, auto-closing pairs, and surrounding pairs.

Changes here should reflect actual `.mtfsnippet` syntax and avoid introducing generic behaviour that does not suit 12d MTF snippets.

### `README.md`

User-facing documentation for the extension.

Keep it practical, clear, and aligned with the current extension features.

### `CHANGELOG.md`

Records user-visible changes.

Update this when making meaningful feature, grammar, snippet, documentation, or packaging changes.

### `test-parameter-regions.mtfsnippet`

Test/sample `.mtfsnippet` file used to check highlighting behaviour.

Use this file when validating grammar changes.

## Language ID

The current language id is:

```text
12dmtfsnippet
````

Do not rename or replace this language id unless explicitly requested.

Changing the language id can break existing user settings, file associations, snippets, grammar links, and documentation.

## Safe Change Rules

Prefer small, focused, reviewable changes.

Before editing, identify which area is affected:

* Manifest/package metadata
* Syntax grammar
* Snippets
* Language configuration
* Documentation
* Packaging scripts
* Test/sample files

Avoid broad rewrites unless explicitly requested.

Do not introduce new build systems, frameworks, dependencies, activation events, commands, or runtime extension code unless explicitly requested.

Do not add TypeScript or JavaScript source files unless explicitly requested.

Do not convert this extension from declarative to runtime-based unless explicitly requested.

## Generated Files

Do not commit generated `.vsix` files.

Generated package files should be treated as build artifacts.

If packaging creates files such as:

```text
*.vsix
```

they should remain uncommitted unless explicitly requested.

Local `.vsix` files may be stored in:

```text
releases/
```

The `releases/` folder is local build/output storage and should remain ignored by Git.

## Publishing / Marketplace Update Workflow

This extension is published manually through the Visual Studio Marketplace publisher portal.

Publisher portal:

```text
https://marketplace.visualstudio.com/manage/publishers/kleberNZ
```

Current manual update process:

1. Package the extension locally:

   ```powershell
   npm run package
   ```

2. Confirm the generated VSIX file exists, for example:

   ```text
   12d-mtf-snippet-0.1.8.vsix
   ```

3. Go to the Visual Studio Marketplace publisher management page:

   ```text
   https://marketplace.visualstudio.com/manage/publishers/kleberNZ
   ```

4. Find the extension:

   ```text
   12d MTF Snippet Support
   ```

5. Click the three-dot menu next to the extension name.

6. Select:

   ```text
   Update
   ```

7. In the upload popup, drop/select the newly generated `.vsix` file.

8. Complete the Marketplace update process in the browser.

Important notes for agents:

* Do not assume Azure DevOps publishing is currently configured.
* Do not introduce an Azure DevOps publishing workflow unless explicitly requested.
* Do not add automated Marketplace publishing unless explicitly requested.
* Treat the current publishing process as manual VSIX upload through the Marketplace publisher portal.
* Generated `.vsix` files must not be committed to Git.
* Local `.vsix` files should be stored in `releases/`, which is ignored by Git.
* Use `npm run package` when preparing a VSIX for Marketplace upload.

## Validation Commands

Use the available npm scripts where relevant:

```bash
npm run check
npm run list
npm run show:files
npm run show:manifest
npm run package
npm run package:clean
```

Suggested validation flow:

```bash
npm run check
npm run show:manifest
npm run show:files
npm run package:clean
```

Use `npm run package` when a normal package build is needed.

Use `npm run package:clean` when checking the package without dependencies.

## Grammar Change Guidance

When editing `syntaxes/12dmtfsnippet.tmLanguage.json`:

* Keep changes narrow and testable.
* Preserve existing scopes unless there is a clear reason to change them.
* Avoid large restructuring unless explicitly requested.
* Test highlighting using real `.mtfsnippet` examples.
* Check `test-parameter-regions.mtfsnippet` after grammar edits.
* Prefer adding specific patterns over broad catch-all patterns.
* Avoid patterns that over-match large regions of the file.

## Snippet Change Guidance

When editing `snippets/mtf.code-snippets`:

* Use clear and predictable snippet prefixes.
* Keep descriptions short and useful.
* Use valid VS Code snippet syntax.
* Keep snippets aligned with documented 12d Model MTF syntax, especially 12d Model Manual Section 19.7.
* Treat snippets as authoring assistance, not abstraction or simplification.
* Avoid adding speculative snippets that are not based on documented syntax or real `.mtfsnippet` workflows.
* Keep placeholder names meaningful.

## README Guidance

When editing `README.md`:

* Keep the documentation user-focused.
* Describe what the extension currently does, not planned features.
* Avoid claiming runtime features that do not exist.
* Keep installation, usage, and feature descriptions consistent with `package.json`.
* Mention `.mtfsnippet` support clearly.
* Keep the README aligned with the Marketplace listing.
* Do not claim validation, linting, formatting, semantic analysis, execution, runtime features, or LSP support unless those features are explicitly added.

## CHANGELOG Guidance

When editing `CHANGELOG.md`:

* Add entries for meaningful user-visible changes.
* Keep entries concise.
* Group changes by version where practical.
* Do not invent release dates or version numbers unless instructed.

## `package.json` Guidance

When editing `package.json`:

* Preserve the `12dmtfsnippet` language id unless explicitly requested.
* Keep grammar, snippet, and language configuration paths consistent with the actual files.
* Do not add activation events unless runtime behaviour is explicitly requested.
* Do not add dependencies unless there is a clear need and explicit approval.
* Keep npm scripts practical and aligned with the current lightweight extension workflow.

## Working Style

Make the smallest change that solves the request.

When proposing changes:

* Explain what changed.
* Mention which files were affected.
* Mention which validation commands were run or should be run.
* Call out any risks, especially changes to `package.json`, grammar scopes, or language id behaviour.

Do not silently make broad structural changes.
