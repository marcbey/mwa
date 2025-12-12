# Moestwanted.Arts Static Site

A multi-page static site for a tattoo studio, built with plain HTML, locally built Tailwind CSS, and Swiper sliders (CDN). German and English variants live side by side.

## Structure
- Root pages: `index.html`, `gallery.html`, `contact.html`, `faq.html`, `about-moe.html`, `impressum.html`
- English pages: `en/` folder mirrors the above
- Assets: `assets/logo`, `assets/images`, fonts/CSS in `assets/`

## Notable behavior
- Home slider uses Swiper with lazy loading; images are defined in markup (`assets/images/mwa-tattoo-home-001..010.jpeg`) and load on demand.
- Gallery page builds its grid from `assets/images/` JPEGs (home 001–010 plus 100–148) and opens a Swiper-based lightbox with lazy loading/preloading.
- Footers auto-fill the current year via a small script.

## Development
- Install deps (Tailwind CLI only): `npm install`
- Build CSS: `npm run build:css` (input `assets/tailwind-input.css` → output `assets/tailwind.css`)
- Open the HTML files or run a simple server:
  - `python -m http.server 3000`
  - Visit `http://localhost:3000/`
- For local file access, some browsers may block fetch/head requests; prefer running a local server for full functionality.

## Adding images
- Home slider: add `assets/images/mwa-tattoo-home-011.jpeg`, `...012.jpeg`, etc. (3-digit, no gaps) and update the slide markup as needed.
- Gallery: add JPEG files following the existing patterns in `assets/images/` and extend the filename list in `gallery.html` / `en/gallery.html` if you want to include more.

## Fonts
- Blank River is hosted locally at `assets/BlankRiver.woff` and wired via `assets/styles.css`; no external font requests are needed.
