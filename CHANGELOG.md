# Changelog

All notable changes to claIDE are documented here.

## v1.2.0

TODO.yaml — Task Tracking
Track project tasks with a TODO.yaml file in your project root. claIDE renders it as an interactive task list — and Claude Code can read and write it naturally as plain YAML.




Interactive task cards
Click any field to edit inline — title, priority, tags, due date, notes. Changes save to disk immediately.





Multi-tag support & tag cloud
Tasks support multiple tags. Add with + button or comma-separated. Tag cloud below the filter bar shows all tags with counts — click to filter, right-click to remove globally.





Markdown notes
Notes are always visible, rendered as markdown. Long notes truncate with a "see more" link. Click to edit raw markdown source.





Sticky controls
Filter bar and tag cloud stick to the top, Add Task button sticks to the bottom — always accessible regardless of scroll position.





Resolution buttons
Mark tasks Active, Deferred (with date picker), Delegated (with name), Done, Canceled, or Not Mine. End-state tasks dim automatically.





Due dates & deferred activation
Overdue tasks highlight red, upcoming tasks amber. Deferred tasks auto-activate when the date arrives.





Archiving
Move completed tasks to todo_archive.yaml via Settings → Todo. Reactivate them anytime from the archive.





Claude-friendly
Settings → Todo generates schema instructions you can paste into CLAUDE.md so Claude knows your priorities and resolutions.



Full guide: Help → TODO.yaml Guide
Settings → Todo
A new Todo tab in Settings lets you fully customize the task system:

Priorities — add, remove, rename, and recolor (critical, high, medium, low, or your own)
Resolutions — define in-progress vs end-state resolutions by sort value
Due soon threshold — how many days before a deadline the amber highlight kicks in
Archive — one-click archive of all end-state tasks
Claude instructions — auto-generated schema text with Copy to Clipboard

Improvements & Fixes
Shift+Enter newline — now sends the correct CSI u escape sequence, fixing newline insertion in Claude Code sessions
Preview pane copy — right-clicking selected text in the preview pane no longer deselects it before copying

## v1.1.20

Terminal Resume
Pick up right where you left off. claIDE can now automatically resume your last Claude session when you switch to an idle terminal — no need to type claude --resume manually.




Auto-resume sessions
Enable in Settings → Behavior → Sessions. When you switch to an idle terminal that had an active Claude session, it automatically resumes.





Right-click → Resume Session
Right-click any terminal in the left sidebar or right-click inside the terminal itself to manually resume the last session on demand.





Seamless context
Your full conversation history, cost, and context window state carry over. Status bar reconnects automatically.



Mermaid Diagrams
claIDE now renders Mermaid diagrams natively — flowcharts, sequence diagrams, ER diagrams, state machines, Gantt charts, and more. Diagrams are plain text, so Claude Code can create and edit them directly.

Open .mmd or .mermaid files with Rendered/Source toggle
Inline ```mermaid blocks render inside markdown
Diagrams preserved in PDF export and rich text copy

Other Features
Markdown frontmatter — YAML frontmatter between --- delimiters is parsed and displayed as a styled key-value table above the rendered content. Included in PDF exports.
Interactive checkboxes — Click checkboxes in rendered markdown to toggle them. Works in both task lists (- [ ]) and table cells. Changes save to disk immediately.
What's New popup — Shows release highlights on first launch of a new version. Also available via Help → What's New.
Source opens editor — Optional setting (Settings → Behavior) to enter edit mode directly when clicking Source in the preview pane.
Unsaved changes prompt — Switching away from edit mode or closing the preview pane prompts to Save, Discard, or Cancel when you have unsaved changes.
Preview refresh — Refresh button in the preview header reloads the file from disk. A "New Version" badge appears automatically when the file changes externally.
Database schema filtering — MCP connections support optional default schemas and databases. List operations filter to just the specified schemas.
Improvements & Fixes
Status bar now uses Claude Code's statusLine API for accurate real-time data
Symlinks in file tree now resolve to their target type (directories expand correctly)
Links in the preview pane open in the OS default browser
Drag and drop from Explorer into the file tree works reliably
Right-click context menu on all pinned files (Copy Filename, Open in Explorer)
Context menus stay within viewport bounds
Updated xterm.js to v6 and all dependencies to latest

## v1.1.20

- Fix context flicker, drag-drop, pinned menus, and changelog generation

## v1.1.19

- Fix terminal right-click crash from keybinding array type mismatch

## v1.1.18

- Add Copy Filename to file tree context menu

## v1.1.17

- Fix status bar, drag-drop, link navigation, and add frontmatter support

## v1.1.16

- Update dependencies including xterm.js v6 and build tooling
- Fix symlink display in file tree and open links in OS browser

## v1.1.15

- Add Mermaid diagram support and multi-schema database filtering

## v1.1.14

- Update README and add xlsx/mammoth dependencies
- Rename status bar label to "Context Remaining"
- Add preview pane copy/paste, context menu, and XLSX/DOCX support
- Add OS file integration to right sidebar
- Update publish workflow to generate changelog and push docs

## v1.1.13

- Add Check for Updates with startup auto-check (Help > Check for Updates)
- Add Skip This Version button to suppress startup notifications for a specific release
- Add View Changes button to open release changelog in browser
- Add Report an Issue menu item (Help > Report an Issue)
- Omit "type": "stdio" from MCP server config for older Claude Code compatibility
- Fix "Behaviour" → "Behavior" spelling throughout docs and Settings UI
- Move release publishing to dedicated workflow
- Add .capture/, .mcp.json, local settings, and build artifacts to .gitignore

## v1.1.12

- Add PDF file preview in FileViewer
- Add Help > Open claIDE Directory menu option
- Fix terminal scroll-to-top: use authoritative lastViewportY for all scroll restore operations, treat position 0 as invalid restore target

## v1.1.11

- Fix terminal scroll-to-top by proactively saving/restoring scroll position before DOM operations
- Save scroll position on terminal instance so it survives across effect re-runs

## v1.1.10

- Add WebGL context loss recovery with automatic fallback to canvas renderer
- Add scroll-to-top guard to detect and correct spurious viewport jumps
- Optimize terminal settings effect to only re-apply when terminal-relevant settings change
- Infer 1M context window from model name and token usage for accurate context % display
- Add MCP server file-based logging and config validation
- Add image, CSV/TSV, SVG, and JSON tree preview support in FileViewer
- Update Claude Config, MCP Config, and Database Editor panels
- Update project documentation

## v1.1.9

- Add right-click Pin/Unpin for files and directories in the file tree sidebar
- Pinned directories expand inline to show contents (same as unpinned directories)
- Add right-click "Open in Explorer" for folders in the file tree
- Add markdown export as PDF via print-friendly hidden BrowserWindow
- Add "Copy as Rich Text" for markdown files (paste into Word, Docs, Slack, etc.)
- Auto-refresh file tree on filesystem changes via recursive fs.watch (debounced 500ms)
- Fix paste hotkey firing twice by preventing browser-level paste event

## v1.1.8

- Add MySQL and SQLite MCP server stubs
- Add Start/Stop MCP button for database connections
- Bug fixes for MCP spawner and database editor

## v1.1.7

- Add multi-database MCP support with PostgreSQL engine
- Database connections support MSSQL and PostgreSQL with engine-specific options
- MCP spawner selects server script based on connection engine

## v1.1.6

- Rewrite MCP server to use low-level Server class, eliminating Zod dependency
- Smaller bundle size and faster startup for database MCP servers

## v1.1.5

- Fix critical DB IPC type mismatches between main and renderer processes
- Fix secret leaks in database connection config
- Fix cross-platform Node.js resolution for MCP server spawning

## v1.1.4

- Bundle MCP server as standalone single file with all dependencies via esbuild
- Eliminate need for separate node_modules in packaged app

## v1.1.3

- Fix Start MCP Server button functionality
- Fix context menu positioning in database editor

## v1.1.2

- Fix macOS compatibility for database features
- Fix database explorer data handling and display

## v1.1.1

- Fix macOS hook routing for Claude Code session tracking
- Improve cross-platform reliability for terminal ID matching

## v1.1.0

- Add MSSQL database integration with built-in MCP server
- Visual database connection editor with test connection
- Database explorer for browsing tables, views, and stored procedures
- Switch CI from upload-artifact to GitHub Releases

## v1.0.18

- Add terminal capture feature with three format options (markdown, markdown+HTML, standalone HTML)
- ANSI color preservation in captures via SGR code parser
- Document capture feature in CLAUDE.md and README

## v1.0.17

- Fix terminal scroll: scroll to bottom on data output, settings fit, and command trigger

## v1.0.16

- Fix terminal scroll: guard DOM swap on re-render, always scroll to bottom on resize

## v1.0.15

- Rewrite README as a full user guide for non-engineers
- Add `>` command palette for memorized commands
- Fix terminal scroll and session replay text wrapping
- Rebrand display name from Claide to claIDE

## v1.0.14

- Add memorized commands: save, manage, and paste common commands per project

## v1.0.13

- Fix persistence: file-backed store replaces localStorage for reliability
- Fix version sync between package.json and app
- Add versioning documentation

## v1.0.12

- Add MCP Config panel for managing MCP servers from the right sidebar
- Server templates for quick setup (GitHub, Playwright, Slack, Postgres, etc.)

## v1.0.11

- Rename project to Claide
- Add application icon
- Add Help > ReadMe menu option

## v1.0.10

- Fix macOS CI: use Python 3.11 for node-gyp compatibility

## v1.0.9

- Fix macOS CI: install setuptools for node-gyp on Python 3.12

## v1.0.8

- Fix macOS terminal: rebuild node-pty from source to produce spawn-helper binary

## v1.0.7

- Fix blank window regression: remove CSP meta tag that blocked scripts in packaged builds

## v1.0.6

- Fix macOS PTY: restore spawn-helper execute bit after ASAR unpack via afterPack hook

## v1.0.5

- Fix macOS shell spawn: drop -i flag, validate shell path

## v1.0.4

- Fix macOS terminal shell init and version sync

## v1.0.3

- Fix macOS x64 artifact glob: electron-builder omits arch suffix for x64

## v1.0.2

- About dialog reads version dynamically from package.json

## v1.0.1

- Configurable key bindings (copy, paste, newline)
- Claude Config panel for editing ~/.claude files from the sidebar
- UX improvements and bug fixes

## v1.0.0

- Initial release
- Terminal-first IDE for Claude Code built with Electron
- Project-aware workspace with multiple terminal sessions
- Claude Code hooks integration for real-time status bar
- File tree browser with pinned Claude config files
- Session replay for reviewing terminal output
