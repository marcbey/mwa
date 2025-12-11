# Moestwanted.Arts Static Site

A multi-page static site for a tattoo studio, built with plain HTML, Tailwind via CDN, and Swiper sliders (CDN). German and English variants live side by side.

## Structure
- Root pages: `index.html`, `gallery.html`, `contact.html`, `faq.html`, `about-moe.html`, `impressum.html`
- English pages: `en/` folder mirrors the above
- Assets: `assets/logo`, `assets/images`, `assets/big-gallery`

## Notable behavior
- Home slider loads images dynamically matching `assets/images/mwa-tattoo-home-XXX.jpeg` (001…); drop new sequential files and they appear automatically.
- Gallery page builds its grid from `assets/big-gallery/*.AVIF` (predefined list in JS) and opens a Swiper-based lightbox to navigate all images.
- Footers auto-fill the current year via a small script.

## Development
- No build step required. Open the HTML files or run a simple server, e.g.:
  - `python -m http.server 3000`
  - Then visit `http://localhost:3000/`
- For local file access, some browsers may block fetch/head requests; prefer running a local server for full functionality.

## Adding images
- Home slider: add `assets/images/mwa-tattoo-home-011.jpeg`, `...012.jpeg`, etc. (3-digit, no gaps).
- Gallery: add AVIF files to `assets/big-gallery/` and reference them in the filenames array inside `gallery.html` (and `en/gallery.html`) if you expand beyond the current list.
