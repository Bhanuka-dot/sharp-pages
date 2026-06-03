# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Sharp Pages** is a static website for a digital product store that sells downloadable resources via Gumroad. The repository currently holds a single styled HTML document — the privacy policy — with no build toolchain, package manager, or backend.

- Store: thesharppages.gumroad.com
- Contact: bhanukaxwayn@gmail.com
- Pinterest API is used for content distribution/pinning

## Repository Contents

- `sharp-pages-privacy-policy.html` — Standalone, self-contained HTML page with all CSS embedded in a `<style>` block. No external JS dependencies.
- `README.md` — Minimal placeholder.

## Design System (used in the HTML)

All styling lives in the `<style>` block of the HTML file. The design tokens are defined as CSS custom properties at `:root`:

| Variable   | Value     | Role                  |
|------------|-----------|----------------------|
| `--ink`    | `#0f0e0c` | Primary text          |
| `--paper`  | `#faf8f4` | Background            |
| `--accent` | `#c8410a` | Brand color (rust)    |
| `--muted`  | `#7a7169` | Secondary text        |
| `--rule`   | `#e4e0d8` | Borders/dividers      |
| `--serif`  | DM Serif Display | Headings       |
| `--sans`   | DM Sans   | Body text             |

Layout is centered at `max-width: 760px`. Sections use a staggered CSS `fadeUp` animation (opacity + translateY) with nth-child delays. `h2` elements have a left accent bar via `::before` pseudo-element using `--accent`.

## Editing the Privacy Policy

The HTML file is self-contained — edit it directly. When adding new policy sections, follow the existing pattern:

```html
<div class="section">
  <h2>Section Title</h2>
  <p>Body text...</p>
  <ul>
    <li>List item</li>
  </ul>
</div>
```

If adding more than 9 sections, extend the `nth-child` animation-delay rules in the `<style>` block (currently covers up to `:nth-child(9)`).

## No Build Step

There is no build process. Preview the file by opening it directly in a browser. No npm, no bundler, no server required.
