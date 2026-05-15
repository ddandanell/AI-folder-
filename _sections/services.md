# Services Section

**Section ID:** `services`
**Schema:** `Service` (per card, optional)
**Variants:** `cards-3` | `cards-4` | `list` | `accordion` | `icon-grid`

---

## Purpose

The Services section communicates **what you do** and **why it matters**. It translates features into benefits and uses micro-copy to pre-qualify visitors and handle early objections.

---

## Variables

```yaml
services_section:
  headline: "Our {Service Category} Services"
  subheadline: "Everything you need, handled by certified professionals."
  layout: "cards-3"    # cards-3 | cards-4 | list | accordion | icon-grid
  cta_inline: true     # Show a CTA button on each service card
  services: []         # Pulled from project-config.md → services[]
```

Per service card:
```yaml
- slug: "{service-slug}"
  name: "{Service Name}"
  short_description: "{1–2 sentences: what it is + main benefit}"
  icon: "{icon-name}"
  image_url: "/images/services/{service-slug}.webp"
  image_alt: "{Service Name} — {brand}"
  cta_text: "Learn More"
  cta_url: "/{service-slug}/"
  highlight: false     # Set true for the most popular service (adds badge)
```

---

## Content Framework

Apply **FAB (Feature → Advantage → Benefit)** to each service card:

```
FEATURE     = What the service IS  (drain cleaning)
ADVANTAGE   = What it DOES better  (removes 99% of blockages permanently)
BENEFIT     = What the customer GETS  (no more slow drains — guaranteed)
```

---

## Copy Example (3-Column Cards)

```markdown
## Our Plumbing Services

Reliable plumbing solutions for homes and businesses in {City}.

### 🔧 Drain Cleaning
Permanently clear clogs with our high-pressure hydro-jetting service. No more slow drains — guaranteed or we come back for free.
[Learn More](/drain-cleaning/)

### 🚰 Leak Detection & Repair
Advanced acoustic leak detection finds hidden leaks before they cause structural damage. Same-day repair available.
[Learn More](/leak-detection/)

### 🏠 Water Heater Services
Installation, repair, and maintenance for tank and tankless water heaters. 10-year parts warranty on new installs.
[Learn More](/water-heater-services/)
```

---

## Rules

- Each service card links to its dedicated pillar page
- Icon or image is required for every card (visual scanning aid)
- Short description: 1–2 sentences max
- "Most Popular" badge highlights the highest-margin service
- Section ends with optional inline CTA: "Not sure which service? [Contact us](#contact) — we'll recommend the right one."

---

## SEO Notes

- H2 should contain primary keyword category ("Plumbing Services")
- Each H3 is an opportunity for a secondary keyword
- Service card copy naturally builds semantic keyword density
- Each `[Learn More]` link contributes to the internal linking graph

---

*Parent: [section-template.md](../_templates/section-template.md) | Used by: [page-template.md](../_templates/page-template.md)*
