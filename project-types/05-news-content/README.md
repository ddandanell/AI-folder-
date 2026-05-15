# Project Type 05: News / Content Platform

**Best for:** Media sites, aggregators, programmatic SEO, high-volume content production, news outlets, and any site generating 100+ pages/month at scale.

**Goal:** Maximize organic traffic volume through high-output content, comprehensive topic coverage, and programmatic page generation. Monetize via display advertising, sponsored content, or subscriptions.

---

## When to Use This Type

- You publish 10+ pieces of content per week
- Content is generated programmatically (from data, APIs, or templates)
- Traffic volume is the primary KPI (not individual conversion rate)
- You want to build a large content moat quickly

---

## Page Structure

```
/ (Homepage — latest + featured content)
├── /news/                         ← News/article index
│   └── /news/{article-slug}/      ← Individual articles
├── /categories/
│   └── /categories/{category}/    ← Category archive pages
├── /tags/
│   └── /tags/{tag}/               ← Tag archive pages
├── /authors/
│   └── /authors/{author}/         ← Author profile pages
├── /topics/
│   └── /topics/{topic}/           ← Topic hub pages (SEO pillar)
├── /data/                         ← Programmatic data pages
│   └── /data/{entity}/            ← Entity-specific data pages
├── /search/                       ← Sitewide search
└── /about/
```

---

## Programmatic Page Generation

This project type is designed for **large-scale programmatic SEO**. Pages are generated from structured data:

```yaml
programmatic_sources:
  - type: "entity-pages"
    data_source: "data/entities.csv"
    template: "pages/templates/entity-page.md"
    url_pattern: "/data/{entity.slug}/"
    estimated_pages: 500

  - type: "location-pages"
    data_source: "data/locations.csv"
    template: "pages/templates/location-page.md"
    url_pattern: "/{topic}/{location.slug}/"
    estimated_pages: 1000

  - type: "comparison-pages"
    data_source: "data/comparisons.csv"
    template: "pages/templates/comparison-page.md"
    url_pattern: "/{item-a}-vs-{item-b}/"
    estimated_pages: 200
```

---

## Content Quality at Scale

Programmatic pages must avoid **thin content penalties**. Minimum requirements per page:

```yaml
programmatic_quality_standards:
  min_word_count: 300
  unique_fields_required: 5     # Must vary per page — not all identical
  unique_intro_required: true   # At least first paragraph must be unique
  schema_required: true
  internal_links_min: 3
  canonical_required: true
```

---

## Ad Monetization Setup

```yaml
advertising:
  provider: "Google AdSense"    # or Mediavine, AdThrive, direct
  ad_placements:
    - position: "header"
      size: "728×90 leaderboard"
    - position: "sidebar"
      size: "300×250 rectangle"
    - position: "in-content"
      frequency: "every 4th paragraph"
      size: "responsive"
    - position: "footer"
      size: "728×90 or responsive"
  lazy_load_ads: true
  ads_txt_file: true
```

---

## Editorial Calendar System

```yaml
editorial_calendar:
  daily_target: 5               # Articles per day
  evergreen_ratio: 0.7          # 70% evergreen, 30% news/trending
  update_schedule:
    evergreen: "every 6 months"
    news: "within 24 hours of event"
  approval_workflow:
    - draft
    - editor-review
    - seo-check
    - publish
```

---

## SEO Strategy

- **Homepage**: Brand + top category keywords
- **Category pages**: Medium-volume category keywords
- **Topic pages**: Broad informational keywords (pillar model)
- **Individual articles**: Long-tail keywords, question keywords
- **Programmatic pages**: Data-driven long-tail coverage at scale
- **Author pages**: E-E-A-T signals, author entity building

---

## Files in This Project Type

- [`structure.md`](./structure.md) — Detailed file/folder structure
- [`pages/article.md`](./pages/article.md) — News article template
- [`pages/category-page.md`](./pages/category-page.md) — Category archive template
- [`pages/programmatic-page.md`](./pages/programmatic-page.md) — Programmatic entity template

---

## Config Overrides

```yaml
project_type: "news-content"
blog_enabled: true
auto_generate_city_pages: false
auto_generate_service_pages: false
auto_generate_keyword_pages: true
cta_form_enabled: false
cta_phone_enabled: false
blog_posts_per_page: 20
```

---

*Parent: [README.md](../../README.md) | Previous: [04-authority-blog](../04-authority-blog/README.md)*
