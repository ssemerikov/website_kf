# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an **Integrated Digital Educational Resource (ICOR)** for § 8 "Quadratic Function, Its Graph and Properties" — a Ukrainian-language educational website for 9th-grade math students. Built as a static site (no build system, no framework), it teaches quadratic functions through interactive theory, simulators, and tests.

**Live site:** https://ssemerikov.github.io/website_kf/

## Running & Testing

- **Local dev:** Open `index.html` directly in a browser, or run `npx serve` / `python3 -m http.server` for a local server
- **No build step, no package manager, no test framework** — this is vanilla HTML/CSS/JS
- **Deployment:** GitHub Pages auto-deploys from the `main` branch on push
- **Math rendering:** KaTeX loads from CDN — verify formulas render correctly when testing changes

## Architecture

```
index.html              ← Landing page (hero, features, progress)
theory/
  index.html            ← Theory sections (5 blocks with sidebar navigation)
  glossary.html         ← Interactive glossary of key terms
practice/
  index.html            ← Simulator hub (3 cards linking to trainers)
  constructor.html      ← Trainer 1: "Parabola Constructor" — Desmos API sliders for a, b, c
  detective.html        ← Trainer 2: "Property Detective" — quiz with Desmos graphs
  dictation.html        ← Trainer 3: "Graphical Dictation" — step-by-step parabola construction
tests/
  index.html            ← Multiple-choice test (3 questions, client-side scoring)
resources/
  links.html            ← Curated links to textbook, Desmos, GeoGebra
styles/
  main.css              ← Global styles, CSS variables, responsive nav, hero, cards, footer
  theory.css            ← Theory page layout (sidebar + content grid), info-boxes, tables
scripts/
  main.js               ← Burger menu toggle + nav animation (only JS file)
```

## Key Technical Details

- **Language:** All content is in Ukrainian (lang="uk"). Keep all UI text in Ukrainian.
- **Desmos API:** Practice pages embed the Desmos Graphing Calculator API v1.9 (key: `dCb31709b45247a7861503a1d66881d2`). Each trainer (`constructor.html`, `detective.html`, `dictation.html`) has its own inline `<script>` that initializes a `Desmos.GraphingCalculator` instance and manages interaction logic.
- **KaTeX:** Theory and test pages load KaTeX from CDN with auto-render. Math uses `$...$` (inline) and `$$...$$` (display) delimiters.
- **CSS:** Design tokens are in `:root` variables in `main.css`. Color scheme: primary `#2c3e50`, secondary `#3498db`, accent `#e67e22`.
- **Responsive:** Mobile breakpoint at 768px with burger nav. Theory sidebar collapses to single column.
- **No shared JS modules:** Each practice page has fully self-contained inline scripts. `main.js` only handles the hamburger menu.

## Development Conventions

- **Source of truth for features/structure:** `plan.md` — it defines the full spec for all sections, simulators, and assessment levels
- **Progress tracking:** `Що зроблено.txt` — a manual changelog of what's been implemented
- **AI-generated content:** Per lab requirements (`Як виконувати завдання.txt`), all materials are created with generative AI assistance and must be verified for mathematical accuracy
- **Commit workflow:** Only commit when explicitly asked. Do not auto-commit.

## Known Issues & TODOs

- Theory page (`theory/index.html`) has duplicate sections — Block 4 "Перетворення" and Block 5 "Цікаво знати" each appear twice (lines ~111-148 and ~137-162)
- The `constructor.html` Desmos calculator doesn't handle the `a = 0` edge case (division by zero in vertex/axis formulas)
- Test page has only 3 questions — the plan specifies multiple difficulty levels (Levels 1-4) that aren't yet implemented
- Progress section on the landing page is hardcoded/static (25%, 10%, 0%) — no actual progress tracking system exists yet
- No offline/Service Worker support yet (listed as a requirement in plan.md)