# Coral Dental — Improved Version (CHANGES.md)

Polished rebuild of the Coral Dental static site (index.html, aligners.html, implants.html).
No 3D added, no frameworks, no build step — plain HTML/CSS/JS, same as the original.
All clinic facts preserved: name, address, phone (+91 98100 47210), prices, doctor credentials.

## Copy fixes (all pages)
- Testimonial typos fixed: "venners"/"veeners" → "veneers", "Shristi" → "Srishti",
  "frorm" → "from", "finnally" → "finally", "Rahhol Sidana" → "Rahul Sidana".
- All six patient reviews lightly proofread for grammar/capitalization (facts unchanged).
- "Clear Teeth Aligners" → "Clear Aligners" everywhere (treatment card, booking
  dropdown + hidden select + default summary + Quick View modal + WhatsApp message
  value + og:title on aligners.html).
- "Mild Cosmetic:" → "Mild Correction:"; "Mild Cosmetic Alignment" →
  "Mild Alignment (Cosmetic Care)"; modal variant → "Mild Alignment (Minor Cosmetic Fix)".
- "100% Numbed" chip/spec → "Painless" / "Fully Painless".
- Credential formatting standardized: "MFD RCS (Ireland)" in body text,
  "MFD RCS (IRELAND)" on hero eyebrow and badges ("FOUNDER • MFD RCS (IRELAND)").
- "35K+ Community" → "35K+ Online Community".
- Address punctuation: "Tri Nagar Delhi, 110035" → "Tri Nagar, Delhi 110035".

## Branding & assets
- Dr. Srishti's photo extracted from the embedded base64 blob into
  `doctor-srishti.jpg` and reused on all three pages (replaces a random stock
  photo that was mislabeled as her on aligners.html/implants.html).
- Dr. Chetna's hotlinked Unsplash stock photo replaced with a branded "DC"
  monogram avatar (honest, no fake identity, zero external dependency).
- Four facility bento images downloaded locally (`facility-*.jpg`) — no more
  Unsplash hotlinks; site now works fully offline except fonts + Three.js CDN.
- New `favicon.svg` (gold tooth on teal) + `theme-color` meta on all pages.
- `og:image` made absolute (https://coraldental.in/8450.webp) for social scrapers.

## Navigation, structure & footer
- All internal links changed from absolute (`/aligners.html`, `/#treatments`, `/`)
  to relative (`aligners.html`, `index.html#treatments`, `index.html`) so the
  site works from any path or opened directly from disk.
- aligners.html and implants.html got a proper full footer (brand, address,
  phone/email/hours, nav to Home + the other 3D guide + Google Business Profile
  + Instagram, legal line) matching the index footer instead of a one-liner.
- Hero video `preload="auto"` → `preload="metadata"`; `loading="lazy"` added to
  all 15 below-fold images.

## Verification performed
- Tag-balance check: all three pages structurally valid, no unclosed/stray tags.
- All referenced local assets (17 images/video/svg) exist on disk.
- Inline JS syntax-checked with node --check on all pages; JSON-LD validated.
- No duplicate element IDs on any page; no leftover typos ("venners",
  "Shristi", "Rahhol", "Clear Teeth", "Mild Cosmetic", "unsplash", absolute
  internal hrefs) — grep-verified clean.
- Not pushed to GitHub (per instructions). Serve the folder with any static
  server, e.g. `python3 -m http.server` inside it.

## Known notes
- The Three.js 3D explorers on aligners.html/implants.html still load from
  cdnjs/jsdelivr CDN (unchanged, as in the original).
- Google Fonts still loaded from CDN; everything else is local.
