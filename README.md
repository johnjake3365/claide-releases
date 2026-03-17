# claIDE

A terminal-first IDE for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) built with Electron.

claIDE wraps Claude Code terminals in a project-aware workspace. The terminal is the primary interaction surface — the UI exists to organize, observe, and navigate Claude Code sessions.

## Download

Go to the [Releases](https://github.com/johnjake3365/claide-releases/releases) page and download the latest installer for your platform:

| Platform | File |
|----------|------|
| Windows | `claIDE-Setup-x.x.x.exe` |
| macOS (Apple Silicon) | `claIDE-x.x.x-arm64.dmg` |

## Features

- **Multi-terminal workspace** — run multiple Claude Code sessions side by side, organized by project
- **Session monitoring** — live status bar showing context usage, cost, model, active tool, and turn count
- **File preview** — view markdown (rendered), code (syntax highlighted), images, SVGs, CSV/TSV tables, JSON trees, and PDFs without leaving the IDE
- **Markdown export** — export rendered markdown as PDF or copy as rich text for sharing
- **Terminal capture** — save terminal output as markdown or HTML with ANSI color preservation
- **Session replay** — replay terminal sessions from raw logs with full formatting
- **File tree** — browse project files with search, pin frequently used files/directories
- **Claude Config panel** — edit `CLAUDE.md`, settings, rules, skills, and agents from the sidebar
- **MCP server management** — add, configure, enable/disable, and health-check MCP servers
- **Database connections** — connect to MSSQL, PostgreSQL, MySQL, and SQLite databases via built-in MCP servers
- **Memorized commands** — save and recall common commands per project via `>` palette
- **Configurable key bindings** — customize copy, paste, newline, and capture hotkeys
- **Theming** — dark (default), light, win95, eclipse, sequoia, and hotdog themes

## Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) must be installed and authenticated
- Node.js 18+ (for Claude Code)

## System Requirements

- **Windows** 10/11 (x64)
- **macOS** 12+ (Apple Silicon)

## License

MIT

## Author

Jake Hayes
