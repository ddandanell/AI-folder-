# News / Content Platform: Structure

---

## Folder Structure

```
project-root/
├── _config/
│   ├── project-config.md
│   └── global-settings.md
│
├── data/                              ← Source data for programmatic pages
│   ├── entities.csv
│   ├── locations.csv
│   ├── comparisons.csv
│   └── categories.json
│
├── pages/
│   ├── index.md                       ← Homepage
│   ├── about/
│   │   └── index.md
│   ├── search/
│   │   └── index.md                   ← Search results page
│   │
│   ├── news/
│   │   ├── index.md                   ← News index (latest, paginated)
│   │   └── {article-slug}/
│   │       └── index.md               ← Individual article
│   │
│   ├── categories/
│   │   ├── index.md                   ← Categories hub
│   │   └── {category-slug}/
│   │       └── index.md               ← Category archive
│   │
│   ├── topics/
│   │   ├── index.md                   ← Topics hub
│   │   └── {topic-slug}/
│   │       └── index.md               ← Topic pillar page
│   │
│   ├── authors/
│   │   ├── index.md                   ← Authors listing
│   │   └── {author-slug}/
│   │       └── index.md               ← Author profile page
│   │
│   └── templates/                     ← Programmatic page templates
│       ├── entity-page.md
│       ├── location-page.md
│       └── comparison-page.md
│
├── images/
│   ├── og/
│   ├── articles/                      ← Featured article images
│   └── authors/
│
└── fonts/
```

---

## Page Inventory

| Page Type | URL Pattern | Index? | Level | Volume |
|-----------|------------|--------|-------|--------|
| Homepage | `/` | Yes | 0 | 1 |
| News Index | `/news/` | Yes | 1 | 1 |
| Article | `/news/{slug}/` | Yes | 2 | High |
| Category | `/categories/{cat}/` | Yes | 1 | Medium |
| Topic Pillar | `/topics/{topic}/` | Yes | 1 | Medium |
| Author Profile | `/authors/{author}/` | Yes | 1 | Medium |
| Programmatic | `/{entity}/` | Yes | 2–3 | Very High |
| Paginated Archive | `/news/page/{n}/` | **No** | — | — |
| Tag Pages | `/tags/{tag}/` | Selective | 2 | High |

---

## Navigation Structure

```
Header:
  Logo | [Topics ▾] | [Categories ▾] | [Authors] | [Search 🔍]

Footer:
  Column 1: Topics (top 6)
  Column 2: Categories (top 6)
  Column 3: Top Authors
  Column 4: About | Contact | Advertise | Privacy | Terms
```

---

## Pagination Rules

```yaml
pagination:
  news_index: 20 posts per page
  category_archive: 20 posts per page
  author_archive: 20 posts per page
  rel_prev_next: true           # Required for paginated SEO
  paginated_pages_index: false  # Paginated pages 2+ are noindex
  canonical_paginated: "first page"
```

---

## Freshness Signals

News/content sites must signal freshness to Google:

```yaml
freshness:
  show_date_published: true
  show_date_modified: true
  schema_date_modified: true
  update_existing_posts: true
  update_frequency: "monthly for evergreen, daily for news"
```

---

*Parent: [README.md](./README.md) | Templates: [pages/article.md](./pages/article.md)*
