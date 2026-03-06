# AI Coding Agent Extension Guide

A static reference site comparing the **Claude Code** and **ChatGPT / Codex** extension ecosystems — covering Commands, MCP/Tools, Skills, Hooks, and Plugins for both platforms.

## Pages

- **Landing Page** — Side-by-side Claude Code vs ChatGPT/Codex entry point
- **Ecosystem Cheatsheets** — Interactive visual maps showing how each platform's extension concepts fit together, ordered by learning sequence
- **Extension Concepts** — Detailed references with summary tables, installation methods, configuration scoping, and popular examples
- **Config Examples** — Real CLAUDE.md and AGENTS.md from this repo shown side by side

## Setup for GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings > Pages**
3. Set Source to **Deploy from a branch**
4. Set Branch to **main** and folder to **/docs**
5. Save — your site will be live in a few minutes

## Setup for Azure Static Web Apps

This repo is configured for Azure Static Web Apps with GitHub Actions. The deployment workflow is in `.github/workflows/azure-static-web-apps-brave-bay-06ce9bf10.yml` and publishes the existing static site directly from `docs/` with no build step.

1. In your Azure Static Web App, copy the deployment token if you do not already have it
2. In GitHub, open **Settings > Secrets and variables > Actions**
3. Add or verify the repository secret named `AZURE_STATIC_WEB_APPS_API_TOKEN_BRAVE_BAY_06CE9BF10`
4. Push to `az-swa` or rerun the workflow on that branch

Branch mapping:

- GitHub Pages: `main`
- Azure Static Web Apps: `az-swa`

Deployment mapping:

- `app_location`: `docs`
- `skip_app_build`: `true`
- `output_location`: empty

## Project Structure

```
docs/
├── index.html                      # Landing page
├── claude-ecosystem-cheatsheet.html   # Claude Code ecosystem (React)
├── claude-concepts.html            # Claude Code concepts reference
├── chatgpt-ecosystem-cheatsheet.html  # ChatGPT/Codex ecosystem (React)
├── chatgpt-concepts.html           # ChatGPT/Codex concepts reference
└── config-examples.html            # CLAUDE.md vs AGENTS.md examples
```

## License

MIT
