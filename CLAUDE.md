# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static HTML/CSS website with no build system, dependencies, or test framework. It is deployed via GitHub Pages directly from the repository root.

## Previewing the Site

Open any HTML file directly in a browser, or serve locally:

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080`.

## Structure

The live site lives at the **repo root**:

- `index.html` — home page
- `about.html` — about page
- `contact.html` — contact page (includes a form)
- `style.css` — single shared stylesheet for all root pages

The `my-project/` subdirectory is an earlier prototype with its own `index.html` and `style.css`. Its nav links still use `#` placeholders and it is **not** part of the deployed site.

## Page Conventions

- Every root-level page uses the same `<header>` + `<nav>` pattern with links to `index.html`, `about.html`, and `contact.html`.
- All pages link `style.css` from the root (`<link rel="stylesheet" href="style.css" />`).
- Footer is fixed to the bottom of the viewport via CSS (`position: fixed; bottom: 0`).
- `index.html` footer includes `.footer-links` nav; `about.html` and `contact.html` footers currently do not — keep this consistent when adding pages.

## CSS Conventions

- Primary color: `#2c3e50` (dark blue-grey) used for header, footer, buttons, and heading text.
- Button hover darkens to `#1a252f`.
- Global reset at the top of `style.css` (`margin: 0; padding: 0; box-sizing: border-box`).
- Avoid inline styles; `about.html` has one (`style="margin-top: 16px; color: #666;"`) that should be moved to `style.css` if the pattern is reused.
