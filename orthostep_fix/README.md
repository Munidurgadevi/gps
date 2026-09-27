# ARTHROSTRIDE / OrthoStep Website

## Project structure

- `index.html` — home page in the project root
- `pages/` — all internal HTML pages
- `assets/css/base.css` — shared styles (reset, design tokens, typography,
  buttons, header/nav, footer, shared responsive breakpoints, dark-mode theme).
  Loaded by every page.
- `assets/css/pages/*.css` — one CSS file per page, containing only styles
  unique to that page (`index.css`, `home2.css`, `products.css`,
  `contact.css`, `insurance.css`, `consultation.css`, `login.css`,
  `signup.css`). Every HTML page loads `base.css` plus its own page file —
  no page shares another page's file, and no rule is duplicated across files.
- `assets/js/main.js` — common interactions (dark-mode toggle, mobile menu,
  password show/hide, scroll reveal)
- `assets/images/` — image assets
- `assets/fonts/` — optional local fonts
- `assets/js/plugins/` — optional JavaScript plugins
- `documentation/` — project documentation

All HTML pages use external CSS only; inline CSS and `<style>` blocks are not
used anywhere.

## Theme / layout notes

- **Dark mode** is implemented with CSS custom properties (`--bg`, `--surface`,
  `--ink`, `--muted`, `--line`, `--shadow`) that cascade through the entire
  stylesheet, so toggling `body.dark` re-themes every page consistently. It
  works correctly across all pages and was kept.
- **RTL mode** was removed. The previous `rtl.css` only patched a handful of
  selectors (nav, hero, footer) and left many components — forms, auth
  screens, absolutely-positioned icons/buttons, product/stat grids — visually
  broken in RTL. Since it did not work properly site-wide, the toggle button,
  its CSS, and its JS logic were removed rather than shipped half-working.
