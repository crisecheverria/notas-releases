# Notas for macOS

Notas is a local-first Markdown notes app for macOS, built with Rust and [GPUI](https://gpui.rs). Your notes are plain `.md` files in a folder you own, and a built-in [MCP](https://modelcontextprotocol.io) server lets AI agents read, search and edit them.

**[Download the latest version](https://github.com/crisecheverria/notas-releases/releases/latest/download/Notas.dmg)** · [All releases](https://github.com/crisecheverria/notas-releases/releases) · [Website](https://cristianecheverria.com/notas)

## Install

1. Download `Notas.dmg` and open it.
2. Drag **Notas** into **Applications**.
3. Open Notas. Your notes are stored in `~/Notas` (you can change the folder with the `NOTAS_DIR` environment variable).

Requires macOS 13 or later. The app is a universal build, so it runs on Apple Silicon and Intel Macs.

### "Notas can't be opened" on first launch

Builds that are not notarized by Apple trigger a macOS warning the first time you open them. Either right-click the app, choose **Open**, then **Open** again, or run:

```bash
xattr -dr com.apple.quarantine /Applications/Notas.app
```

Releases that say "notarized" in their notes open normally.

## What you get

- Edit, split and preview modes with autosave, and syntax highlighting for about 35 languages
- Notebooks (folders), tags, pinned notes, `[[wiki links]]` and image paste
- `⌘P` fuzzy finder, optional Vim mode and a full-width focus mode
- An MCP server (`notas-mcp`, bundled inside the app) with 15 tools for AI agents

## Connect an AI agent

The app includes the MCP server. Open **Notas → MCP Server…** (`⌘,`) to copy a ready-made config, or for Claude Code run:

```bash
claude mcp add notas -- /Applications/Notas.app/Contents/MacOS/notas-mcp --vault ~/Notas
```

## Feedback

Questions and bug reports are welcome in this repository's [issues](https://github.com/crisecheverria/notas-releases/issues).

## Verify your download

Each release lists the SHA-256 of `Notas.dmg`:

```bash
shasum -a 256 ~/Downloads/Notas.dmg
```
