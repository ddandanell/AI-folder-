# Landing Page Structure

Complete file and folder structure for a Landing Page project type.

---

## Folder Structure

```
project-root/
├── _config/
│   ├── project-config.md          ← Fill in all fields
│   └── global-settings.md         ← Framework defaults
│
├── pages/
│   ├── index.md                   ← The landing page itself
│   ├── thank-you.md               ← Post-conversion page (no-index)
│   └── privacy.md                 ← Privacy policy (required for ads)
│
├── _sections/                     ← From framework root _sections/
│   (Use: hero, cta, faq, testimonials)
│   (Do not use: services, about, contact — embed these inline)
│
├── images/
│   ├── og/
│   │   └── default.jpg            ← 1200×630 OG image
│   ├── hero/
│   │   └── hero-main.webp         ← Hero background or feature image
│   └── testimonials/              ← Testimonial photos (optional)
│
└── fonts/                         ← Self-hosted fonts (WOFF2 format)
```

---

## Page Inventory

| Page | URL | Index? | Level | Priority |
|------|-----|--------|-------|---------|
| Landing Page | `/` | Yes | 0 | 1.0 |
| Thank You | `/thank-you/` | **No** | — | — |
| Privacy Policy | `/privacy/` | Yes | — | 0.1 |

---

## Navigation Structure

Landing pages deliberately **omit the standard navigation** to prevent visitors from leaving before converting.

```
Header:  Logo (links to /) + Phone number (CTA) — nothing else
Footer:  Privacy Policy link + Copyright — nothing else
```

---

## Internal Linking (Minimal)

Since landing pages have only 1–2 pages, internal linking is minimal:

- Logo in header → links to `#hero` (scrolls to top, keeps user on page)
- All CTAs → link to `#contact` anchor on the same page
- Thank You page → links back to `/` (in case user wants to return)

---

## A/B Testing Slots

Landing pages benefit from systematic A/B testing. Define test variants here:

```yaml
ab_tests:
  - id: "hero-headline-v1"
    element: "hero.headline"
    variant_a: "Original headline text"
    variant_b: "Alternative headline text"
    metric: "form_submission"

  - id: "cta-button-color"
    element: "cta.button_background"
    variant_a: "#0055FF"
    variant_b: "#FF5500"
    metric: "click_rate"
```

---

*Parent: [README.md](./README.md) | Pages: [pages/landing-page.md](./pages/landing-page.md)*
