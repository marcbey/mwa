You are an expert front-end developer. The project is a production-ready static website for a tattoo studio. The stack is plain HTML + Tailwind (CDN) with light vanilla JS and Swiper (CDN). German pages live at root; English mirrors are in `en/`.

## Pages
- `index.html` / `en/index.html`: Home with headline and a Swiper slider. The slider auto-populates from sequential files `assets/images/mwa-tattoo-home-XXX.jpeg` (001+) so new images appear without code changes; ~3 images visible on desktop. Below is a two-column section with intro text and a linked Moe portrait.
- `gallery.html` / `en/gallery.html`: Responsive grid (1–3 cols) of AVIF images from `assets/big-gallery/` (filenames listed in JS). Lazy-loaded via IntersectionObserver. Clicking opens a full lightbox with Swiper arrows to navigate all images; backdrop closes on click; ESC/close button supported.
- `contact.html` / `en/contact.html`: Headline + 4 large CTA buttons (Email, Instagram, WhatsApp, Linktree) in 1 col on mobile, 2 cols on larger screens.
- `faq.html` / `en/faq.html`: Accordion FAQ (details/summary) using provided German/English content (German text preserved verbatim). Headline styled with Blank River font.
- `about-moe.html` / `en/about-moe.html`: Portrait of Moe with provided biography text, CTA to gallery.
- `impressum.html` / `en/impressum.html`: Impressum content, dark themed like other pages.

## Shared layout & design
- Dark background with `assets/logo/studio.jpg` and black overlay; white text; system font stack (`-apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`).
- Sticky header with logo `assets/logo/mwa-logo-white.avif`, nav links (`Gallery`, `FAQ`, `Contact & Booking`), Instagram icon (https://www.instagram.com/mwa.tattoo), and mobile menu toggle. Links use root-relative paths (e.g., `/gallery` → `gallery.html`).
- Footer: dark, centered text, bullet separator, Impressum link, dynamic year via inline script (`© <span id="year"></span> Moestwanted.Arts • Impressum`). Year auto-fills on load.
- Tailwind loaded via CDN on every page. Swiper CSS/JS loaded where sliders are used (home, gallery lightbox). Custom arrow styling matches the home slider (subtle translucent round buttons).

## Assets
- Logo: `assets/logo/mwa-logo-white.avif`
- Background: `assets/logo/studio.jpg`
- Home slider images: `assets/images/mwa-tattoo-home-XXX.jpeg` (sequential, 3-digit)
- Gallery images: `assets/big-gallery/*.AVIF` (filenames enumerated in JS)
- Moe portrait: `assets/logo/moe.jpg`
- Favicon: `assets/logo/elmo-2.jpg`

## Behavior notes
- Home slider images link to `/gallery`.
- Gallery lightbox supports arrow navigation; pagination dots removed.
- Mobile menus toggle via simple JS; layout is one-column with header on top, footer at bottom; pages are responsive.

## Running locally
- No build step. Open the HTML or run a simple server, e.g. `python -m http.server 3000` and visit `http://localhost:3000/`.
