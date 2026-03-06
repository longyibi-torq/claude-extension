# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static reference site comparing the Claude Code and ChatGPT/Codex extension ecosystems. The site covers Commands, MCP/Tools, Skills, Hooks, and Plugins for both platforms via interactive cheatsheets and concept reference pages.

## Architecture

- **Static HTML site** — no build step, no framework, no bundler
- All pages are self-contained HTML files with inline CSS and JS
- Served via GitHub Pages from the `docs/` directory on the `main` branch
- The two ecosystem cheatsheets use React 18 (loaded via CDN/UMD) with Babel standalone for JSX transform; the other pages are plain HTML

## Key Files

- `docs/index.html` — Landing page with side-by-side Claude Code vs ChatGPT/Codex columns
- `docs/claude-ecosystem-cheatsheet.html` — Interactive React app: visual map of the Claude Code extension ecosystem
- `docs/claude-concepts.html` — Detailed reference for Claude Code extension concepts (plain HTML)
- `docs/chatgpt-ecosystem-cheatsheet.html` — Interactive React app: visual map of the ChatGPT/Codex ecosystem
- `docs/chatgpt-concepts.html` — Detailed reference for ChatGPT/Codex extension concepts (plain HTML)
- `docs/config-examples.html` — Side-by-side CLAUDE.md vs AGENTS.md examples with tabbed UI

## Development

No build or install step. Open any HTML file directly in a browser or use a local server:

```
python -m http.server 8000 --directory docs
```

Validate changes manually — check links, responsive layout, and interactive cheatsheet behavior. Confirm no JS console errors.

## Conventions

- Each page is a standalone HTML file — styles and scripts are inlined, not shared
- Claude Code brand color: `#d97757`
- OpenAI brand color: `#10a37f`
- 2-space indentation for HTML/CSS/JS
- Lowercase hyphenated filenames with platform prefix (e.g. `claude-concepts.html`, `chatgpt-ecosystem-cheatsheet.html`)
- When renaming published files, update all incoming links in `index.html` and this file
