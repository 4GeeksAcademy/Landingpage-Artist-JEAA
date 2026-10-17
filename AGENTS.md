# AGENTS.md

## Project Overview

**Landing page for the artist "pericolospalotes"** built on the 4Geeks Academy HTML/CSS starter template.

- **Type:** Static HTML/CSS/JS landing page (optionally with Tailwind CSS)
- **Served by:** Python Flask (`server.py`)
- **Entry point:** `index.html` (must contain the basic HTML structure)

## Rules & Conventions

- Only work with HTML and CSS; do not incorporate any other technology such as JavaScript or frameworks to develop it.

### HTML
- `index.html` must always keep a valid basic HTML structure: `<!DOCTYPE html>`, `<html>`, `<head>` (with `charset`, `viewport`, `<title>`) and `<body>`.
- Keep the `<head>` section for metadata and external resources only.
- Create as many additional HTML files as needed.
- Always use semantic HTML tags where possible.
- Use schema.org markup tags (e.g. `itemscope`, `itemtype`, `itemprop`).
- Use accessibility tags for blind people.
- Tags must be organized according to their hierarchy.
- Must be screen-reader friendly, using `aria-label` attributes and alternative texts (`alt`).

### CSS
- Create CSS files and import them into the website using a `<link>` tag placed between the `<head></head>` tags.
- Follow the naming convention `styles*.css` (e.g. `styles.css`) unless another name is explicitly agreed.
- Use plain, well-organized CSS. Avoid inline styles unless strictly necessary.
- CSS styles must generate a modern and attractive style.

### Tailwind (optional)
- If Tailwind CSS is used, add it via the official Tailwind CSS v4 CDN inside the `<head>`:
  ```html
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
  ```

### JavaScript
- Use `<script>` tags or external `.js` files as appropriate.
- Keep JavaScript unobtrusive and separated from HTML markup.

### Development Server
- Run the site locally with:
  ```bash
  $ pip3 install flask && python3 server.py
  ```
- The server runs on port `3000` and serves static files from the project root with caching disabled.

### Files & Structure
- Do not modify `server.py`, `learn.json`, or the README files unless the task explicitly requires it.
- Keep all static assets (images, fonts, etc.) in the project root or dedicated folders (e.g. `assets/`, `images/`).

## Workflow Recommendations
- After any change, validate the HTML/CSS rendering by running the dev server.
- Keep changes minimal and scoped to the task — do not add or modify anything that was not requested.