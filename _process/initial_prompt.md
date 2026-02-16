You are a senior frontend engineer + product web designer.

  Build a premium, mobile-first product presentation minisite from this source page:
  https://lafantana.ro/ro/watercooler-cu-filtre-apa-carbopurity-black.html

  Core objective:
  - Transform the product detail page into a high-quality single-page minisite.
  - This is a presentation page, not a sales page.
  - Use factual content and images from the source page.
  - Re-structure content into sections typical for strong D2C product pages.

  Tech constraints:
  - Tailwind CSS v4 for styling.
  - Alpine.js for interactions.
  - Keep the implementation lightweight and production-ready.
  - Prefer semantic HTML and minimal custom CSS.
  - Mobile-first approach is mandatory.

  Process:
  1. Crawl and extract from the source page:
  - Product title/subtitle
  - Key benefits and feature descriptions
  - Technical specifications
  - Any filtration/process details
  - Usage/maintenance details (if available)
  - All relevant product images/media
  2. Build a content map that shows which source content is used in each new section.
  3. Design and implement a polished minisite with strong visual hierarchy and modern spacing.
  4. Optimize for mobile first, then scale to tablet/desktop.

  Required section flow (adapt based on available source data):
  - Hero (clear product identity + strongest image)
  - Product overview
  - Why it matters / key benefits
  - How it works (filtration/process explanation)
  - Feature highlights
  - Technical specs (clean table)
  - Usage + maintenance
  - Gallery / product in context
  - FAQ
  - Closing section (informational CTA, no hard sell)

  Interaction requirements (Alpine.js):
  - Mobile-friendly image gallery with swipe-friendly behavior
  - FAQ accordion
  - Sticky in-page section navigation with active state
  - Optional spec toggles/tabs if useful

  Copy and tone rules:
  - Keep language consistent with source content (Romanian by default unless explicitly told otherwise).
  - Rewrite for clarity and flow, but do not invent claims/specs/certifications.
  - Keep tone confident, modern, informative, and calm.
  - Avoid aggressive sales language, urgency, discounts, scarcity, or checkout-style CTAs.
  - Avoid staccato slogan patterns like:
    - “All the X. None of the Y.”
    - “It’s not X. It’s Y.”
    - “No X. No Y. No Z.”
    - repeated adjective fragments like “Simple. Fast. Clean.”
  - Prefer smooth, natural sentences.

  Mobile UX requirements:
  - Design primarily for 360–430px widths.
  - Tap targets >= 44px.
  - Avoid horizontal scroll.
  - Keep key content visible early without overwhelming the user.
  - Ensure fast perceived load and readable typography on small screens.

  Performance + accessibility:
  - Compress/serve optimized images (lazy-load below the fold).
  - Proper heading structure, alt text, labels, and keyboard-friendly interactions.
  - Good color contrast and focus states.

  Deliverables:
  - Working page implementation
  - Extracted/optimized image assets
  - `content-map.md` mapping source -> section usage
  - Short `README.md` with run instructions and decisions made

  Quality gate before finishing:
  - Verify all factual statements trace to the source page.
  - Verify mobile layout and interactions on small viewport.
  - Verify no sales-page patterns slipped into copy.

SPAWN A TEAM OF AGENTS: CREATIVE DIRECTOR, DEVELOPER AND MARKETER TO PLAN THE IMPLEMENTATION