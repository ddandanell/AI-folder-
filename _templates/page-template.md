# Page Template

Every generated page is built from this template. Variables in `{curly_braces}` are injected from `_config/project-config.md` and the page's own front matter.

---

## Front Matter (Required for Every Page)

```yaml
---
# Identity
page_type: "{homepage|pillar|city|keyword|blog|faq|contact}"
slug: "/{slug-here}"
canonical: "{domain}{slug}"
level: 0   # 0=homepage, 1=pillar, 2=sub, 3=supporting

# SEO
title: "{Primary Keyword} | {Brand Name}"
description: "{Action verb} + {main benefit} in {location if local}. {Soft CTA}."
robots: "index, follow"
primary_keyword: "{exact target keyword}"
secondary_keywords:
  - "{secondary keyword 1}"
  - "{secondary keyword 2}"

# Open Graph
og_title: "{title}"
og_description: "{description}"
og_image: "/images/og/{slug}.jpg"
og_type: "website"

# Schema
schema_types:
  - "{Schema type 1}"
  - "{Schema type 2}"

# Sections (ordered list of sections to include)
sections:
  - hero
  - services
  - about
  - testimonials
  - cta
  - faq
  - contact

# Internal Links
parent_page: "/{parent-slug}"
child_pages:
  - "/{child-slug-1}"
  - "/{child-slug-2}"
related_pages:
  - "/{related-slug-1}"

# Dates
date_created: "YYYY-MM-DD"
date_modified: "YYYY-MM-DD"
---
```

---

## Page Body Structure

```markdown
# {H1: Primary Keyword — matches title tag, do not repeat brand name}

<!-- SECTION: hero -->
{{> sections/hero}}

<!-- SECTION: services -->
{{> sections/services}}

<!-- SECTION: cta (repeat) -->
{{> sections/cta variant="minimal"}}

<!-- SECTION: about -->
{{> sections/about}}

<!-- SECTION: testimonials -->
{{> sections/testimonials}}

<!-- SECTION: cta (full) -->
{{> sections/cta variant="full"}}

<!-- SECTION: faq -->
{{> sections/faq}}

<!-- SECTION: contact -->
{{> sections/contact}}
```

---

## H Tag Hierarchy Rule

```
H1 — One per page. Exact or near-exact primary keyword.
H2 — Section titles. Target secondary keywords or question-format.
H3 — Subsection titles. Long-tail variants, supporting topics.
H4 — Rarely used. Only for nested content (e.g., nested FAQ).
```

---

## Word Count Targets by Page Type

| Page Type | Min Words | Target Words |
|-----------|-----------|-------------|
| Homepage | 800 | 1,200 |
| Pillar/Service | 1,200 | 2,000 |
| City Page | 600 | 1,000 |
| Keyword Page | 600 | 900 |
| Blog Post | 1,500 | 2,500+ |
| FAQ Page | 800 | 1,500 |

---

## CTA Placement Rules

1. **Above the fold** — visible without scrolling (in Hero section)
2. **Mid-page** — after the Services section (minimal variant)
3. **Bottom** — full CTA section before Contact
4. **In-content** — one contextual CTA per 400 words of body text

---

*Parent: [FRAMEWORK.md](../FRAMEWORK.md) | See also: [section-template.md](./section-template.md) | [metadata-template.md](./metadata-template.md)*
