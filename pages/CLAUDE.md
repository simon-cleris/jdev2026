# Pages

One markdown file per slide, numbered in presentation order. Each file is imported by the root entry through a `src:` reference, and the root entry is the only place where the order is defined.

## Conventions

- File name: two-digit order prefix, then a short snake_case description.
- Every slide declares a custom layout from the `layouts/` folder in its frontmatter. Never use the `none` layout.
- Slide text is written in French, code and comments in English.
- Reusable blocks are Vue components from the `components/` folder, not copied markup.
- Progressive reveal uses the `clicks` frontmatter key together with `v-click` on each block.
- Images are served from the public assets folder and referenced with an absolute `/assets/` path.
- Sources are listed at the bottom of the slide with the `slide-sources` block.

## Content blocks

- `Card` and `CardOutline` wrap markdown content as a left-accented card or an outlined highlight.
- Free-form grids use plain divs with the shared utility classes from the global stylesheet.
