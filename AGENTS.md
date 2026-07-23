# AGENTS.md

This file provides guidance to Codex (Codex.ai/code) when working with code in this repository.

## Project Overview

Static developer portfolio website for Sebastian Hauss (Fullstack Developer, Vienna). No build tools, bundlers, or package managers — pure HTML/CSS served directly from the filesystem or a static host.

## Structure

```
index.html          # Homepage with terminal-style info widget
pages/
  projects.html     # Project cards grid
  contact.html      # Contact links
CSS/
  main.css          # Single stylesheet for the entire site
img/                # Tech stack icons and social icons
doc/                # CV PDF
```

## Development

Open any `.html` file directly in a browser, or use a local static server:

```
npx serve .
# or
python -m http.server
```

No build step, no compilation, no dependencies to install.

## Formatting

Always format files with Prettier after editing, using the project's `.prettierrc`:

```
npx prettier --write .
```

## Architecture Notes

- **Single CSS file** (`CSS/main.css`) styles all three pages. Path is `CSS/main.css` from root or `../CSS/main.css` from `pages/`.
- **Color palette** follows Nord-inspired tones: background `#eceff4`, dark text `#2e3440`, accent blue `#5e81ac`/`#339af0`, terminal background `#4c566a`.
- **Typography**: JetBrains Mono loaded from Google Fonts — used sitewide for the developer/terminal aesthetic.
- **Terminal widget** on the homepage (`index.html`) is pure CSS — the typewriter animation on the name uses `@keyframes type` + `@keyframes cursor`; the blinking cursor uses `@keyframes blink`.
- **Project cards** (`pages/projects.html`) use a CSS Grid layout (`.projects-grid`) with `<article class="project-card">` elements. Each card has a `.project-header` (tech icons + title) and `.project-content` (description + GitHub link).
- Responsive breakpoints at `768px` and `480px` in `main.css`.
