# Carbopurity Black — Product Minisite

Premium product presentation minisite for the **Carbopurity Black** watercooler by La Fântâna.

## Quick Start

Open `index.html` in any modern browser. No build step required.

For local development with live reload:

```bash
# Using Python
python3 -m http.server 8000

# Using Node.js
npx serve .
```

Then open `http://localhost:8000` in your browser.

## Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **Tailwind CSS** | v4 (Browser CDN) | Utility-first styling with custom theme |
| **Alpine.js** | v3 (CDN) | Lightweight interactivity |
| **Alpine.js Collapse** | v3 (CDN) | Smooth FAQ accordion animations |
| **Inter** | Google Fonts | Typography (weights 400–800) |

## Architecture Decisions

### Single HTML file
The entire minisite is a single `index.html` file with no build step. Tailwind v4's browser CDN compiles styles at runtime during development. For production, this can be switched to a CLI build to reduce CSS payload.

### Dark theme as default
The product is called "Carbopurity **Black**" — the dark palette (Rich Black `#0A0A0A`, Charcoal `#1A1A1A`, Cyan accent `#30C6FF`) reinforces the product identity and creates a premium feel.

### Alpine.js over a full framework
Alpine.js provides just enough interactivity (gallery, FAQ accordion, sticky nav, scroll animations) without the overhead of React/Vue. All components are defined as plain functions in a single `<script>` block.

### Image strategy
- Hero image is preloaded and eager-loaded for fast LCP
- All below-fold images use native `loading="lazy"`
- Gallery uses full-size, medium, and thumbnail variants
- YouTube video is lazy-loaded (thumbnail shown first, iframe injected on click)

### Content in Romanian
All copy is in Romanian, consistent with the source page. Content has been rewritten for clarity and flow but all facts trace back to the source page (see `content-map.md`).

### No sales patterns
The page is informational, not transactional. No pricing, no urgency language, no discount codes, no checkout CTAs. The closing section uses a soft "Solicită informații" CTA.

## Project Structure

```
launch-carbopurity-black/
├── index.html              # Single-page minisite
├── content-map.md          # Source → section content mapping
├── README.md               # This file
└── assets/
    └── images/
        ├── hero/           # Main product hero image
        ├── gallery/        # Gallery images (full, medium, thumbnails)
        ├── icons/          # Service/benefit icons from source
        └── specs/          # Technical diagrams (CO2 bottle)
```

## Sections

1. **Hero** — Product identity with main image and ambient glow
2. **Product Overview** — Three key pillars (3-in-1 water, NSC filter, UV)
3. **Key Benefits** — Six benefit cards with icons
4. **How It Works** — Four-step filtration process + CO2 highlight
5. **Feature Highlights** — Bento grid with key stats (600L, 5600L)
6. **Technical Specs** — Expandable specification table
7. **Usage & Maintenance** — Installation and service timeline
8. **Gallery** — Swipeable image carousel with lightbox + YouTube embed
9. **Reviews** — Two verified customer reviews
10. **FAQ** — Eight-item accordion
11. **Closing CTA** — Soft informational CTA with trust indicators

## Interactive Features

- **Sticky navigation** with active section tracking via IntersectionObserver
- **Mobile section pills** that appear on scroll (scrollable horizontal strip)
- **Image gallery** with touch swipe, thumbnail strip, and fullscreen lightbox
- **FAQ accordion** with smooth collapse animation (Alpine.js Collapse plugin)
- **Spec toggle** — progressive disclosure of full technical specifications
- **Scroll reveal** — sections fade up on scroll entry (respects `prefers-reduced-motion`)
- **Lazy YouTube embed** — loads iframe only on click

## Accessibility

- Semantic HTML5 with proper heading hierarchy (single `<h1>`, `<h2>` per section)
- `aria-labelledby` on every section
- `aria-expanded` and `aria-controls` on FAQ accordion
- `role="dialog"` and `aria-modal="true"` on lightbox
- Keyboard-navigable: Tab, Enter/Space, Escape
- Focus-visible ring styles on all interactive elements
- `prefers-reduced-motion` disables all animations
- Color contrast: white on dark exceeds WCAG AAA (19.4:1)

## Production Optimization

To switch from Tailwind CDN to a production build:

```bash
npx @tailwindcss/cli -i ./input.css -o ./assets/css/output.css --minify
```

Then replace the `<script src="...@tailwindcss/browser@4">` tag with a `<link rel="stylesheet" href="assets/css/output.css">` tag. This reduces CSS from ~300KB (runtime) to ~10–15KB (tree-shaken).
