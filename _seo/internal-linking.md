# Internal Linking

The complete internal linking system for the framework. Every link is intentional, tracked, and follows the rules below.

---

## 1. Why Internal Linking Matters

Internal links do three things:
1. **Pass authority** (PageRank) from high-authority pages to target pages
2. **Help Google discover** and understand the page hierarchy
3. **Guide users** through a conversion journey

A well-linked site is a **graph, not a tree**. Every node (page) connects to multiple others in logical, topical, and geographic patterns.

---

## 2. Link Hierarchy Rules

```
Homepage          → links DOWN to all Pillar pages (and top city pages)
Pillar Page       → links DOWN to sub-pages, city pages, related blog posts
City Page         → links UP to parent Pillar, ACROSS to nearby city pages
Sub-Service Page  → links UP to Pillar, across to related sub-services
Blog Post         → links UP to Pillar, across to 2–3 related posts
FAQ Page          → links to relevant service pages and city pages
Contact Page      → links to Homepage and primary service Pillar
```

**Rule:** No page should be more than **3 clicks from the homepage**.

---

## 3. Hub-and-Spoke Model

```
         [Pillar: /plumbing-services/]
              ↑        ↑        ↑
   /drain-cleaning/  /leak-detection/  /water-heater/
```

- The Pillar page is the **hub** — it links out to all spokes and receives links back
- Each spoke (sub-service) covers a focused subtopic
- The hub concentrates authority and ranks for broad terms
- The spokes rank for specific terms and push authority back up

---

## 4. Geographic Cluster Model

```
         [Pillar: /plumbing-services/]
              ↑        ↑        ↑
    /plumbing-austin/  /plumbing-dallas/  /plumbing-houston/
         ↕                  ↕                    ↕
    (nearby cities cross-link within 50km radius)
```

- City pages link UP to the service pillar
- City pages cross-link to geographically nearby city pages (max 3 cross-links per page)
- City pages link DOWN to any city-specific sub-service pages (e.g., `/drain-cleaning-austin/`)

---

## 5. Topic Cluster Model (Blog)

```
      [Pillar: /plumbing-services/]
              ↑
    [Blog: "How to unclog a drain"]
    [Blog: "Water heater cost guide"]
    [Blog: "Signs you need a new pipe"]
```

- Every blog post must link to its parent pillar page with a contextual CTA
- Blog posts can cross-link to 2–3 related blog posts on the same subtopic
- Blog posts should NOT link to competitor sites unless citing a statistic

---

## 6. Anchor Text Rules

Use varied anchor text to avoid over-optimization penalties:

| Type | Percentage | Examples |
|------|-----------|---------|
| Exact match | 30% | "drain cleaning austin" |
| Partial match | 40% | "our drain cleaning services", "professional plumbers in austin" |
| Generic | 20% | "learn more", "click here", "our team", "get a quote" |
| Branded | 10% | "AcmePlumb", "AcmePlumb Austin" |

**Never use the same anchor text for the same destination more than twice on a single page.**

---

## 7. Link Count Rules

| Page Type | Min Links Out | Max Links Out | Min Links In |
|-----------|-------------|-------------|-------------|
| Homepage | 10 | 20 | — (builds naturally) |
| Pillar Page | 8 | 15 | 3 |
| City Page | 5 | 10 | 2 |
| Blog Post | 5 | 12 | 1 |
| Supporting Page | 3 | 8 | 1 |

---

## 8. Contextual vs. Navigation Links

| Type | Location | SEO Weight | Example |
|------|----------|-----------|---------|
| Contextual | In body content | **Highest** | "Our [drain cleaning]('/drain-cleaning/') team..." |
| Section CTA | In CTA sections | High | "Explore our [services]('/services/')" |
| Navigation | Header / footer / breadcrumb | Medium | Top nav menu items |
| Sidebar | Related posts widget | Low-medium | "Related: Water Heater Guide" |

**Rule:** Contextual links (in body text) carry the most SEO weight. Always prefer in-content links over navigation links for target pages.

---

## 9. Orphan Page Prevention

An **orphan page** has no internal links pointing to it — Google may never find or rank it.

**Prevention protocol:**
1. Every new page must be linked from at least one existing page before publishing
2. The sitemap serves as a fallback, but sitemap-only discovery is weak
3. Run a monthly orphan check with a crawler (Screaming Frog, Ahrefs Site Audit)
4. High-value new pages (city pages, service pages) must be linked from the homepage or pillar page immediately

---

## 10. Internal Linking Automation Rules

When `auto_internal_linking: true` in `project-config.md`, the system applies these rules automatically:

```yaml
auto_linking_rules:
  - trigger: "mention of {service.name} in body text"
    action: "link first occurrence to /{service.slug}/"
    max_per_page: 2

  - trigger: "mention of {city.name} in body text"
    action: "link first occurrence to /{primary_service}/{city.slug}/"
    max_per_page: 1

  - trigger: "end of every body section"
    action: "inject minimal CTA linking to #contact"
    max_per_page: 3

  - trigger: "blog post published in topic {topic}"
    action: "add to related posts on pillar page for {topic}"
    max_per_pillar: 10
```

---

## 11. Internal Link Audit Checklist

Run this audit monthly:

```
[ ] No orphan pages (every page has ≥1 internal link pointing to it)
[ ] No broken internal links (404 responses)
[ ] No redirect chains (A → B → C — consolidate to A → C)
[ ] Homepage links to all pillar pages
[ ] Every city page links to its parent pillar page
[ ] Every blog post links to at least one service pillar page
[ ] No page exceeds 20 internal outbound links
[ ] Anchor text distribution is within target ratios
[ ] No two pages compete for the same primary keyword (see keyword-strategy.md)
```

---

*Parent: [seo-framework.md](./seo-framework.md) | See also: [keyword-strategy.md](./keyword-strategy.md)*
