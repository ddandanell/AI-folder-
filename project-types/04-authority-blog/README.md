# Project Type 04: Authority Blog / Content Site

**Best for:** Building topical authority in a niche, content marketing, affiliate websites, thought leadership platforms, and any site where organic search traffic is the primary objective.

**Goal:** Become the most comprehensive and trusted resource on a topic. Rank for thousands of informational and commercial keywords. Monetize via ads, affiliate, leads, or products.

---

## When to Use This Type

- Content is your primary product (not a physical service)
- You want to rank for informational keywords at scale
- You are building affiliate revenue, ad revenue, or brand awareness
- You want to establish topical authority before targeting commercial keywords

---

## Page Structure

```
/ (Homepage — brand + niche overview)
├── /blog/                         ← Blog index (latest posts)
│   └── /blog/{post-slug}/         ← Individual blog posts
├── /{pillar-topic-1}/             ← Pillar content page (hub)
│   └── /blog/                     ← Cluster posts feed into pillar
├── /{pillar-topic-2}/
├── /about/
├── /resources/                    ← Tools, guides, downloads
│   └── /resources/{resource}/
├── /newsletter/                   ← Email capture
└── /contact/
```

---

## Content Hierarchy

```
Pillar Page (broad topic, 2000–4000 words)
   ↑↑↑ receives links from all cluster posts
   │
   ├── Cluster Post 1 (subtopic A, 1500–2500 words) → links to Pillar
   ├── Cluster Post 2 (subtopic B, 1500–2500 words) → links to Pillar
   ├── Cluster Post 3 (subtopic C, 1500–2500 words) → links to Pillar
   └── Cluster Post N ...
```

---

## Content Strategy

### Content Pillars (Choose 3–5 Topics)

Each pillar represents a major topic cluster the site will own:

```yaml
pillars:
  - slug: "pillar-1"
    name: "Pillar Topic 1"
    primary_keyword: "{broad keyword}"
    target_posts: 20     # Cluster posts to support this pillar
  - slug: "pillar-2"
    name: "Pillar Topic 2"
    primary_keyword: "{broad keyword}"
    target_posts: 15
```

### Post Types

| Type | Purpose | Length |
|------|---------|--------|
| Ultimate Guide | Comprehensive overview — targets broad keyword | 3000–5000w |
| How-To | Process-based — targets "how to" keywords | 1500–2500w |
| Listicle | Curated list — targets "best X" keywords | 1500–3000w |
| Comparison | X vs. Y — targets commercial investigation keywords | 1500–2500w |
| Case Study | Story-based proof — builds trust and shares | 1000–2000w |
| News/Update | Time-sensitive — targets trending searches | 500–1000w |

---

## Monetization Integration

### Affiliate Links

```yaml
affiliate_rules:
  - disclose_at_top: true          # Required by FTC
  - nofollow_all_affiliate: true   # Required for Google compliance
  - max_affiliate_links_per_post: 5
  - disclosure_text: "This post contains affiliate links. If you click and buy, we may earn a commission at no extra cost to you."
```

### Email Capture

Every post includes an email opt-in via:
- Inline content upgrade (related freebie)
- Exit-intent popup
- End-of-post newsletter CTA

---

## SEO Strategy

- **Pillar pages**: Broad T1/T2 keywords
- **Cluster posts**: Specific T2/T3/T4 long-tail keywords
- **All posts**: Link to pillar page (hub-and-spoke model)
- **Update cadence**: Refresh posts older than 12 months to maintain rankings

---

## Files in This Project Type

- [`structure.md`](./structure.md) — Detailed file/folder structure
- [`pages/pillar-page.md`](./pages/pillar-page.md) — Pillar/hub page template
- [`pages/blog-post.md`](./pages/blog-post.md) — Blog post template

---

## Config Overrides

```yaml
project_type: "authority-blog"
blog_enabled: true
auto_generate_city_pages: false
auto_generate_service_pages: false
auto_generate_keyword_pages: true
cta_form_enabled: false
cta_phone_enabled: false
```

---

*Parent: [README.md](../../README.md) | Previous: [03-local-seo](../03-local-seo/README.md) | Next: [05-news-content](../05-news-content/README.md)*
