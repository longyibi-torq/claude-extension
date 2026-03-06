# Repository Guidelines

## Project Structure & Module Organization
This repository is a static documentation site served from `docs/` via GitHub Pages. The main entry point is `docs/index.html`. Platform-specific reference pages live alongside it:

- `docs/claude-ecosystem-cheatsheet.html`
- `docs/claude-concepts.html`
- `docs/chatgpt-ecosystem-cheatsheet.html`
- `docs/chatgpt-concepts.html`

There is no `src/` or shared asset pipeline. Each page is self-contained with inline HTML, CSS, and JavaScript, so changes usually stay within a single file.

## Build, Test, and Development Commands
No install or build step is required.

- `python -m http.server 8000 --directory docs` runs the site locally from the published folder.
- Open `http://localhost:8000` to verify navigation and layout.
- `git status` checks that only intended documentation files changed before committing.

## Coding Style & Naming Conventions
Use standard HTML, CSS, and vanilla JavaScript with consistent 2-space indentation. Keep pages standalone: prefer inline styles and scripts over introducing shared build tooling. Name new pages descriptively with lowercase hyphenated filenames, following the existing pattern such as `chatgpt-concepts.html`.

Preserve the established brand colors when editing comparison content:

- Claude: `#d97757`
- OpenAI: `#10a37f`

## Testing Guidelines
There is no automated test suite in this repository. Validate changes manually in a browser using the local server. Check links, responsive layout, and any interactive cheatsheet behavior on the page you edited. If you add JavaScript, confirm it works without console errors.

## Commit & Pull Request Guidelines
Recent history uses short, imperative commit messages such as `update pages` and `Add company logos, doc links, and redesign index page`. Follow that style: start with a verb and keep the subject concise.

Pull requests should include:

- A brief summary of what changed
- The pages affected under `docs/`
- Screenshots or GIFs for visible UI/layout updates
- Any GitHub Pages impact, especially if navigation or published filenames changed

## Deployment Notes
GitHub Pages should publish from the `main` branch using the `/docs` folder. Avoid renaming published files unless you also update incoming links and homepage navigation.
