# The Resonance of Tuesday – Website

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status: Live](https://img.shields.io/badge/Status-Live%20(Feb%202025)-brightgreen)](https://www.amazon.com/Resonance-Tuesday-structural-accidentally-holographic-ebook/dp/B0GNNZZB4G/)
![Tech: HTML5](https://img.shields.io/badge/Stack-HTML5%20%7C%20Tailwind%20%7C%20JavaScript-orange)
![Author: Alec Borman](https://img.shields.io/badge/Author-Alec%20Borman-lightgrey)

This repository contains the source code for the promotional website of the book *The Resonance of Tuesday* by Alec Borman. The site is a single‑page experience that presents book excerpts through a terminal‑style interface, includes a reactive companion character ("The Foreman"), and provides direct links to purchase the ebook, paperback, or hardcover on Amazon.

**Live links:**  
- [Ebook](https://www.amazon.com/Resonance-Tuesday-structural-accidentally-holographic-ebook/dp/B0GNNZZB4G/)  
- [Paperback](https://www.amazon.com/Resonance-Tuesday-structural-accidentally-holographic/dp/B0GNP9K547/)  
- [Hardcover](https://www.amazon.com/Resonance-Tuesday-structural-accidentally-holographic/dp/B0GNP9GL1M/)

---

## Table of Contents
- [Features](#features)
- [Tech Stack](#tech-stack)
- [File Structure](#file-structure)
- [Design System](#design-system)
  - [Colors](#colors)
  - [Typography](#typography)
  - [Visual Effects](#visual-effects)
- [Interactive Components](#interactive-components)
  - [Fidelity Toggle](#fidelity-toggle)
  - [Reading Terminal](#reading-terminal)
  - [The Foreman](#the-foreman)
  - [Purchase Cards](#purchase-cards)
- [JavaScript Overview](#javascript-overview)
  - [Icon Rendering](#icon-rendering)
  - [Note Expansion](#note-expansion)
  - [Chapter Storage](#chapter-storage)
- [Maintenance](#maintenance)
  - [Updating Amazon Links](#updating-amazon-links)
  - [Updating Prices](#updating-prices)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## Features
- **Single‑file HTML** – All markup, styles, and scripts in one file for easy deployment.
- **Blueprint grid background** – CSS‑generated graph‑paper effect.
- **Fidelity toggle** – Switches between a blurred “Low Fidelity” mode and a sharp “High Fidelity” mode.
- **Chapter reader** – Three book excerpts displayed in a terminal, with expandable footnotes (“system notes”).
- **The Foreman** – A fixed bottom‑right character that delivers typewriter messages in response to user actions.
- **Purchase cards** – Three cards (ebook, paperback, hardcover) with prices and direct Amazon links.
- **Responsive** – Built with Tailwind CSS (CDN) and works on mobile devices.

---

## Tech Stack
- **HTML5**
- **Tailwind CSS** (via CDN) – utility classes plus custom CSS variables.
- **Vanilla JavaScript** – no frameworks.
- **Lucide Icons** – SVG icons rendered client‑side.

---

## File Structure
The entire project is contained in `index.html`:
```
index.html
├── <head>         – meta, Tailwind, custom <style>
├── <body>         – UI components
│   ├── Navbar
│   ├── Hero (fidelity toggle)
│   ├── Terminal reader (#read)
│   ├── The Foreman (fixed)
│   └── Purchase cards (#buy)
└── <script>       – all JavaScript logic
```

---

## Design System
Custom CSS is defined in the `<style>` block using CSS variables.

### Colors
| Variable          | Value      | Usage |
|-------------------|------------|-------|
| `--blueprint-blue`| `#0f172a`  | Page background |
| `--primary-cyan`  | `#22d3ee`  | Accents, links, terminal headers |
| `--secondary-yellow`| `#eab308`| Warnings, paperback card |
| `--grid-line`     | `rgba(56, 189, 248, 0.1)` | Grid overlay colour |

### Typography
- **`'JetBrains Mono'`** – used for all terminal text and The Foreman.
- **`'Inter'`** – reserved for high‑level UI (largely overridden by mono).

### Visual Effects
**Blueprint grid** – created with two linear gradients:
```css
background-image:
  linear-gradient(var(--grid-line) 1px, transparent 1px),
  linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
background-size: 40px 40px;
```

**Fidelity blur** – elements with class `.blur-target` are affected by the toggle:
- Low Fidelity: `filter: blur(3px); opacity: 0.7;`
- High Fidelity: `filter: blur(0); opacity: 1;`

---

## Interactive Components

### Fidelity Toggle
Located in the hero section, the checkbox `#signal-toggle` switches the class `.high-fidelity` on the `<body>`. It updates the status indicator and triggers The Foreman to comment.

### Reading Terminal
The `#read` section contains a terminal that displays chapter excerpts.
- Chapters are stored as HTML strings in a JavaScript object `chapters`.
- `loadChapter(num)` fades out the current content, replaces it, and fades in.
- **System notes** – Clickable words inside the text toggle the visibility of corresponding note elements (styled as ASCII trees). Helper functions `createTrigger(id, word)` and `createNote(...)` generate the necessary HTML.

### The Foreman
A fixed element at the bottom‑right that:
- Slides into view 1.5 seconds after page load.
- `typeWriter(text)` clears and types a message character‑by‑character (30ms interval).
- Reacts to chapter changes, fidelity toggles, and note expansions.

### Purchase Cards
Three cards in the `#buy` section, each with:
- Format name (Ebook, Paperback, Hardcover)
- Price ($2.99, $14.99, $24.99)
- An “Acquire” button linking to the corresponding Amazon product page.

---

## JavaScript Overview

### Icon Rendering
`lucide.createIcons()` is called on page load to replace `<i data-lucide="...">` elements with SVG icons.

### Note Expansion
The “Expand All Notes” button toggles all system notes:
- If any note is closed → opens all notes, button text becomes `[-] COLLAPSE`.
- If all notes are open → closes all notes, button text becomes `[+] EXPAND`.

### Chapter Storage
Chapters are stored as raw HTML strings inside the `chapters` object:
```js
const chapters = {
  1: `<p>... content ...</p>`,
  2: `...`,
  3: `...`
};
```

---

## Maintenance

### Updating Amazon Links
Locate the three `<a>` tags inside the `#buy` section. Update the `href` attributes with the new ASINs or full URLs. Current links are:

- **Ebook:** `https://www.amazon.com/Resonance-Tuesday-structural-accidentally-holographic-ebook/dp/B0GNNZZB4G/`
- **Paperback:** `https://www.amazon.com/Resonance-Tuesday-structural-accidentally-holographic/dp/B0GNP9K547/`
- **Hardcover:** `https://www.amazon.com/Resonance-Tuesday-structural-accidentally-holographic/dp/B0GNP9GL1M/`

### Updating Prices
Find the `<div>` elements displaying the prices (e.g., `$2.99`) in each card and edit the text accordingly.

---

## License
This project is licensed under the MIT License – see the [LICENSE](LICENSE) file.

---

## Acknowledgements
- [Lucide Icons](https://lucide.netlify.app/)
- [Tailwind CSS](https://tailwindcss.com/)
- [JetBrains Mono](https://www.jetbrains.com/lp/mono/)

---

**Created by Alec Borman**  
For questions or permissions, please contact [your email].
