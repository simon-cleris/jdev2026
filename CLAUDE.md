# PROJECT

This project is a conference support presentation built with Slidev.

## Framework

Slidev (Vite + Vue + Markdown). Entry point: `slides.md`.

## Architecture

- `slides.md` — headmatter only (theme, transition, mdc, drawings) + list of `src:` imports
- `pages/` — one `.md` file per slide section
- `components/` — reusable Vue components used across slides
- `layouts/dark-slide.vue` — custom layout providing the dark background (`#0f172a`) and base text color shared by all content slides
- `assets/` — video files referenced by slides

## Patterns

- Global config (theme, transition, mdc, drawings) lives in the headmatter of `slides.md` only, never in imported pages.
- All content slides use `layout: dark-slide`. Do not use `layout: none`.
- Do not repeat `background: #0f172a` or `color: #e2e8f0` as inline styles on root divs — the layout handles it.
- Reusable slide structures go into `components/` as Vue SFCs.
