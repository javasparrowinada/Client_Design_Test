# CLAUDE.md

## Project Overview

This repository contains the marketing landing page for **Javasparrow** (ジャバスパロー), a Japanese product design consulting company. The page is titled "なぜ、同じ機能なのに「選ばれる製品」と「埋もれる製品」に分かれるのか v2" and serves as a sales/lead-generation page showcasing the company's design expertise.

## Repository Structure

```
Client_Design_Test/
├── index.html    # Single-page static landing page (HTML + embedded CSS + minimal JS)
├── CLAUDE.md     # This file
└── .git/
```

This is a minimal, zero-dependency project consisting of a single HTML file with embedded CSS and JavaScript.

## Tech Stack

- **HTML5** with semantic markup (lang="ja")
- **Vanilla CSS** embedded in `<style>` tags (no preprocessors)
- **No JavaScript frameworks** — minimal inline JS only
- **Google Fonts** (Noto Serif JP, Noto Sans JP) loaded via CDN
- **No build system** — the file is served as-is
- **No package manager** — no `package.json`, no npm/yarn dependencies

## Development Workflow

### Running Locally

Open `index.html` directly in a browser. No build step, dev server, or compilation is required.

### Making Changes

All content, styles, and scripts live in `index.html`. When editing:

1. Modify the single `index.html` file
2. Refresh the browser to see changes
3. Test at both desktop and mobile widths (breakpoint: 600px)

### No Build/Test/Lint Commands

There are no build, test, or lint commands configured for this project. Changes are validated visually in the browser.

## Code Architecture

### HTML Sections (in order)

| Section | CSS Class | Purpose |
|---------|-----------|---------|
| Header | `.header` | Achievement notification banner |
| Hero | `.hero` | Page title with gradient background |
| Article | `.article` | Main content wrapper (7 subsections) |
| Company | `.company-section` | Company info, features, and awards (dark bg) |
| CTA | `.cta-section` | Call-to-action for free consultation |
| Footer | `.footer` | Company name and copyright |

### CSS Design System

**Color palette** (defined as CSS custom properties on `:root`):

| Variable | Value | Usage |
|----------|-------|-------|
| `--color-bg` | `#FAFAF8` | Page background |
| `--color-bg-section` | `#F5F4F0` | Section backgrounds |
| `--color-text` | `#2C2C2C` | Primary text |
| `--color-text-secondary` | `#5A5A5A` | Secondary text |
| `--color-accent` | `#1A3A5C` | Primary accent (dark blue) |
| `--color-accent-light` | `#2D5A8A` | Lighter accent |
| `--color-highlight` | `#C4A962` | Gold highlight |
| `--color-border` | `#E0DED8` | Borders |
| `--color-negative` | `#C45C5C` | Red emphasis |

**Typography**:
- Headings: `'Noto Serif JP'` (serif)
- Body: `'Noto Sans JP'` (sans-serif)
- Responsive sizing via `clamp()`

**Layout techniques**: CSS Grid, Flexbox, media queries

**Responsive breakpoint**: `max-width: 600px` (single breakpoint, mobile-first adjustments)

### CSS Features Used

- CSS custom properties (variables)
- CSS Grid and Flexbox
- `clamp()` for fluid typography
- Keyframe animations (`fadeInUp`)
- Gradient backgrounds
- Box shadows and backdrop filters

## Conventions

### Content Language

All user-facing content is in **Japanese**. Code comments and technical identifiers (class names, CSS variables) are in **English**.

### CSS Class Naming

Classes use a flat, descriptive naming convention (e.g., `.hero-title`, `.survey-box`, `.case-study-card`, `.process-step`). The pattern resembles BEM but without strict `__` / `--` separators.

### File Organization

Everything is in a single file. If the project grows, consider splitting into:
- `styles.css` for CSS
- `script.js` for JavaScript
- An `assets/` directory for images

### Git Commit Style

Commits use short, imperative-mood messages describing the change (e.g., "Update title in index.html to include 'v2'").

## Key Considerations for AI Assistants

1. **Single file project** — all changes happen in `index.html`. Be cautious with large edits as the file is ~1,193 lines.
2. **Japanese content** — text content is in Japanese. Preserve existing Japanese text accurately when making edits.
3. **No tests or linting** — validate changes by visual inspection. Ensure HTML is well-formed.
4. **Responsive design** — any layout changes must work at both desktop and mobile widths (600px breakpoint).
5. **CSS variables** — use the existing design tokens (CSS custom properties) rather than hardcoding colors or sizes.
6. **External dependency** — Google Fonts is the only external resource. The page should work offline except for font loading.
7. **Static hosting** — no server-side logic. The page must function as a standalone HTML file.
