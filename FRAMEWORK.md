# Framework Architecture

This document defines the complete system architecture, philosophy, and operating rules for the AI-Folder scalable digital framework.

---

## 1. System Philosophy

The framework treats every website as a **digital machine** — not a collection of pages. Each component (page, section, schema, link) is a cog in a larger engine designed to:

- Rank in search engines through interconnected SEO structures
- Convert visitors through psychology-driven layouts and copy frameworks
- Scale automatically when new locations, services, or keywords are added
- Minimize manual rebuilding between projects

**The AI agent must think as:**
- **System Architect** — designing the structure before writing a single word
- **SEO Strategist** — planning how every page supports every other page
- **UX Designer** — ensuring the user's journey from landing to conversion is frictionless
- **Conversion Optimizer** — applying proven persuasion frameworks (AIDA, PAS, BAB) to every section
- **Project Manager** — enforcing consistency, naming conventions, and modularity

---

## 2. Core Data Flow

```
project-config.md
       │
       ▼
page-generator.md  ──►  generates page stubs (MD files)
       │
       ▼
page-template.md   ──►  each page pulls in section blocks
       │
       ├──► _sections/hero.md
       ├──► _sections/services.md
       ├──► _sections/testimonials.md
       ├──► _sections/faq.md
       └──► _sections/cta.md
       │
       ▼
metadata-template.md  ──►  injects title, description, schema, canonical
       │
       ▼
internal-linking.md   ──►  injects contextual links between pages
       │
       ▼
Final rendered page (HTML / static site output)
```

---

## 3. Page Hierarchy Model

Every project uses a strict **4-level page hierarchy**:

```
Level 0 ──  Homepage  (brand authority + primary keyword)
   │
Level 1 ──  Pillar Pages  (main service / category)
   │
Level 2 ──  Sub-Pages  (service variation / city / subtopic)
   │
Level 3 ──  Supporting Pages  (long-tail keyword / FAQ / blog post)
```

**Linking rule:** Lower-level pages always link UP to their parent. Higher-level pages link DOWN selectively. No page links sideways unless it is a programmatic local SEO cluster.

---

## 4. SEO Structure Model

Each page must define and satisfy four SEO layers:

| Layer | Elements | Source |
|-------|----------|--------|
| On-Page | Title tag, H1, meta description, URL slug | `metadata-template.md` |
| Semantic | H2/H3 structure, LSI keywords, entity mentions | `keyword-strategy.md` |
| Technical | Schema markup, canonical tag, robots, sitemap | `schema-templates.md` |
| Authority | Internal links pointing in, anchor text, topical cluster | `internal-linking.md` |

---

## 5. Section System

Sections are the **atomic units** of every page. They are defined in `_sections/` and composed into pages using the page template.

### Available Sections

| Section | File | Purpose |
|---------|------|---------|
| Hero | `_sections/hero.md` | First impression, primary CTA |
| Services | `_sections/services.md` | Service/feature showcase |
| About | `_sections/about.md` | Trust and credibility |
| Testimonials | `_sections/testimonials.md` | Social proof |
| FAQ | `_sections/faq.md` | Objection handling + FAQ schema |
| CTA | `_sections/cta.md` | Conversion anchor |
| Contact | `_sections/contact.md` | Lead capture form |

### Section Composition Rules

- Hero is **always first**
- CTA appears **after every major section** (not just at the bottom)
- FAQ uses **FAQPage schema** automatically
- Testimonials use **Review schema** automatically
- No section is mandatory except Hero and one CTA

---

## 6. Conversion Psychology Framework

Every page follows the **AIDA-PAS hybrid** model:

```
AWARENESS    ──  Hero section: bold promise, primary keyword, emotional hook
INTEREST     ──  Services / Features: what you do and why it matters
DESIRE       ──  About + Testimonials: why YOU specifically (trust + proof)
ACTION       ──  CTA section: clear, low-friction next step
──────────────────────────────────────────────────────────
PROBLEM      ──  Embedded in hero subheadline and FAQ
AGITATION    ──  Embedded in service descriptions (pain → solution)
SOLUTION     ──  Embedded in CTA copy and testimonials
```

---

## 7. URL and Naming Convention

```
Homepage:          /
Pillar Page:       /{primary-service}/
City Page:         /{primary-service}/{city}/
Keyword Page:      /{primary-service}/{keyword-modifier}/
Blog Post:         /blog/{topic-slug}/
FAQ Page:          /faq/
Contact Page:      /contact/
```

**Rules:**
- All slugs are lowercase, hyphenated
- No stop words in slugs (the, a, an, of, in)
- City name always comes AFTER the service in URL
- Keyword modifier pages target long-tail variants of the primary service

---

## 8. Internal Linking Strategy

See `_seo/internal-linking.md` for the complete linking matrix. Summary:

- **Hub-and-spoke**: Pillar pages link to all sub-pages; sub-pages link back to pillar
- **Geographic clusters**: City pages cross-link to nearby city pages + their parent pillar
- **Topic clusters**: Blog posts link to the pillar page they support
- **Anchor text variation**: 30% exact match, 40% partial match, 30% generic/branded
- **Link depth rule**: No valuable page more than 3 clicks from homepage

---

## 9. Metadata Standards

Every page must include:

```yaml
title: "{Primary Keyword} | {Brand Name}"          # 50-60 characters
description: "{Action verb} + {benefit} + {CTA}"   # 150-160 characters
canonical: "https://domain.com{/slug}"
og:title: "{Same as title or variation}"
og:description: "{Same as description or variation}"
og:image: "/images/og/{slug}.jpg"                  # 1200×630px
robots: "index, follow"
```

---

## 10. Schema Markup Standards

All schemas are defined in `_seo/schema-templates.md`. Required schemas by page type:

| Page Type | Required Schemas |
|-----------|-----------------|
| Homepage | Organization, WebSite, SiteNavigationElement |
| Service Page | Service, LocalBusiness (if local) |
| City Page | LocalBusiness, GeoCoordinates |
| Blog Post | Article, BreadcrumbList |
| FAQ Page | FAQPage |
| Contact Page | ContactPage, LocalBusiness |

---

## 11. Scalability Rules

1. **Never hard-code a city, service, or keyword** — always pull from config
2. **New location = new MD file in cities/** — no other changes needed
3. **New service = new MD file in services/** — links auto-populate via rules
4. **New keyword page = copy keyword-page-template.md** — fill in variables
5. **Batch generation**: The automation system can generate 100+ pages from a single city/service list

---

## 12. Project Type Selection Guide

| Signal | Project Type |
|--------|-------------|
| Single offer, single conversion goal | Landing Page |
| Multiple services, ongoing lead gen | Service Business |
| Physical locations, "near me" queries | Local SEO |
| Long-form content, topical authority | Authority Blog |
| High-volume, programmatic content | News / Content Platform |

---

*Return to [README.md](./README.md) | Next: [_config/project-config.md](./_config/project-config.md)*
