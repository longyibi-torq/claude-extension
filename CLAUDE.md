# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static reference site comparing the Claude Code and ChatGPT/Codex extension ecosystems. The site covers Commands, MCP/Tools, Skills, Hooks, and Plugins for both platforms via interactive diagrams and concept reference pages.

## Architecture

- **Static HTML site** — no build step, no framework, no bundler
- All pages are self-contained HTML files with inline CSS and JS
- Served via GitHub Pages from the `docs/` directory on the `main` branch

## Key Files

- `docs/index.html` — Landing page with side-by-side Claude Code vs ChatGPT/Codex columns
- `docs/claude-ecosystem-diagram.html` — Interactive visual map of the Claude Code extension ecosystem
- `docs/claude-concepts.html` — Detailed reference for Claude Code extension concepts
- `docs/chatgpt-ecosystem-diagram.html` — Interactive visual map of the ChatGPT/Codex ecosystem
- `docs/chatgpt-concepts.html` — Detailed reference for ChatGPT/Codex extension concepts

## Development

No build or install step. Open any HTML file directly in a browser or use a local server:

```
# From repo root
python -m http.server 8000 --directory docs
```

## Conventions

- Each page is a standalone HTML file — styles and scripts are inlined, not shared
- Claude Code brand color: `#d97757`
- OpenAI brand color: `#10a37f`
