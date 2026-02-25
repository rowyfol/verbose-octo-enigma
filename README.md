# Signal & Noise — 80s-Style Personal Website

A retro 80s-styled static website for sharing electrical engineering notes, project builds, personal musings, and a photo gallery. No backend, no frameworks — just HTML, CSS, and JavaScript.

## Features

- **Lab Notes** — EE concepts with LaTeX formulas, code blocks, and technical details
- **Projects** — Build logs with schematics, component lists, and calculations
- **Musings** — Personal thoughts about shows, quotes, and life
- **Gallery** — Image gallery with lightbox viewer
- **File-based CMS** — Content is written in `.txt` files with a simple custom syntax
- **80s Retro Aesthetic** — CRT scanlines, neon accents, pixel fonts, and warm color palette
- **LaTeX Support** — Powered by KaTeX for beautiful math rendering
- **No Backend** — Pure static site, works from any web server or `file://`

## Quick Start

Serve the directory with any static file server:

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .

# PHP
php -S localhost:8080
```

Then open `http://localhost:8080` in your browser.

## Content Format

Content lives in the `content/` directory. Each section has its own folder with an `index.txt` listing the posts and individual `.txt` files for each post.

### Directory Structure

```
content/
├── lab-notes/
│   ├── index.txt              # List of post slugs (one per line)
│   ├── ohms-law-deep-dive.txt
│   └── rc-circuit-analysis.txt
├── projects/
│   ├── index.txt
│   ├── led-matrix-display.txt
│   └── audio-amplifier-build.txt
├── musings/
│   ├── index.txt
│   ├── stranger-things-upside-down.txt
│   └── back-to-the-future-thoughts.txt
└── gallery/
    └── index.txt              # Uses [image] blocks directly
```

### Post File Syntax

Each `.txt` file has a **frontmatter** header and a **body** with typed blocks:

```
---
title: My Post Title
date: 2026-01-15
tags: circuits, resistors
excerpt: A brief description for the listing page
---

[text]
Regular paragraph text. Supports **bold**, *italic*, `inline code`,
and [links](https://example.com).

[heading] Section Title

[latex]
V = IR

[image]
src: images/photo.jpg
caption: My circuit board

[code]
console.log("hello world");

[quote]
"Any sufficiently advanced technology is indistinguishable from magic."

[list]
- Item one
- Item two
- Item three

[divider]
```

### Adding New Content

1. Create a new `.txt` file in the appropriate `content/` folder
2. Add the filename (without `.txt`) to that folder's `index.txt`
3. Refresh the page — your new post appears!

## Tech Stack

- **HTML5 / CSS3 / Vanilla JavaScript** — No frameworks
- **KaTeX** — LaTeX math rendering (loaded via CDN)
- **Google Fonts** — Press Start 2P (pixel), IBM Plex Mono, Space Grotesk