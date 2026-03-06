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

Use these commands in Git Bash to create an Azure Static Web App for this repo and publish the static files from `docs/`.

```bash
az login
az account show
az extension add --name staticwebapp --upgrade

export RG="rg_app_hosting"
export APP_NAME="swa_ai_docs"
export LOCATION="eastus2"
export REPO_URL="https://github.com/longyibi-torq/claude-extension.git"
export BRANCH="main"

az staticwebapp create \
  --name "$APP_NAME" \
  --resource-group "$RG" \
  --location "$LOCATION" \
  --source "$REPO_URL" \
  --branch "$BRANCH" \
  --app-location "docs" \
  --login-with-github
```

After Azure creates the resource and GitHub connection:

1. Open the generated workflow in `.github/workflows/`
2. Confirm it deploys the existing static site with:
   - `app_location: "docs"`
   - `output_location: ""`
   - `skip_app_build: true`
3. Commit and push the workflow to `main`

```bash
git checkout main
git pull origin main
git add .github/workflows
git commit -m "Add Azure Static Web Apps deployment"
git push origin main
```

To get the deployed hostname:

```bash
az staticwebapp show \
  --name "$APP_NAME" \
  --resource-group "$RG" \
  --query "defaultHostname" \
  -o tsv
```

Deployment mapping:

- Branch: `main`
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
