# SEO Framework

The complete on-page, technical, and strategic SEO ruleset for all projects in this framework.

---

## 1. Topical Authority Model

Every project must build **topical authority** — ranking for an entire topic cluster, not just individual keywords. This means:

1. **Pillar Page** — one comprehensive page covering the main topic broadly
2. **Cluster Pages** — multiple supporting pages covering subtopics in depth
3. **Internal Links** — all cluster pages link to the pillar; pillar links to clusters

```
Pillar: /plumbing-services/
  ├── Cluster: /drain-cleaning/
  ├── Cluster: /leak-detection/
  ├── Cluster: /water-heater-services/
  └── Cluster: /emergency-plumbing/
```

---

## 2. Keyword Targeting Strategy

### Keyword Tiers

| Tier | Volume | Intent | Difficulty | Used For |
|------|--------|--------|-----------|---------|
| T1 | High | Transactional | High | Homepage, Pillar Pages |
| T2 | Medium | Commercial | Medium | Service Pages, City Pages |
| T3 | Low | Informational | Low | Blog Posts, FAQ Pages |
| T4 | Very Low | Long-tail | Very Low | Supporting Pages, FAQ items |

### Keyword Assignment Rules

- Each page targets **exactly one primary keyword** (T1 or T2)
- Each page targets **3–5 secondary keywords** (T2 or T3)
- Primary keyword appears in: Title, H1, first 100 words, meta description, image alt, URL slug
- Secondary keywords appear in: H2/H3 subheadings, body paragraphs, FAQ questions
- No two pages target the same primary keyword (keyword cannibalization prevention)

---

## 3. On-Page Optimization Checklist

For every page before publishing:

```
[ ] Title tag: 50–60 chars, primary keyword in first 30 chars
[ ] Meta description: 150–160 chars, includes keyword + CTA
[ ] H1: one per page, matches or near-matches primary keyword
[ ] H2s: target secondary keywords, framed as questions where possible
[ ] First paragraph: contains primary keyword within first 100 words
[ ] Images: all have keyword-aware alt text
[ ] Internal links: minimum 5, maximum 20
[ ] Outbound links: 1–2 authoritative sources per 1,000 words
[ ] URL slug: short, lowercase, hyphenated, includes primary keyword
[ ] Canonical tag: set to the page's own URL
[ ] Schema: correct schema type injected (see schema-templates.md)
[ ] Page speed: LCP < 2.5s, FID < 100ms, CLS < 0.1
[ ] Mobile: fully responsive, no horizontal scroll
[ ] Word count: meets minimum for page type (see page-template.md)
```

---

## 4. Content Depth Requirements

Each piece of content must satisfy **searcher intent** at the correct depth:

| Intent Type | What to Cover | Depth |
|-------------|--------------|-------|
| Informational | Explain the topic fully, answer questions | Comprehensive |
| Commercial | Compare options, explain benefits, handle objections | Persuasive |
| Transactional | Clear offer, pricing context, fast conversion path | Concise + CTA-focused |
| Navigational | Brand/location confirmation, contact info | Brief + trust signals |

---

## 5. Semantic SEO

Beyond keywords, pages must build **semantic relevance** by including:

- **Entities**: Named people, places, organizations relevant to the topic
- **LSI Keywords**: Conceptually related terms that appear naturally (not forced)
- **NLP-friendly formatting**: Short paragraphs, clear H tag hierarchy, bullet points for lists
- **E-E-A-T signals**: Experience (case studies, photos), Expertise (credentials, qualifications), Authoritativeness (reviews, mentions), Trustworthiness (privacy policy, secure forms, license info)

---

## 6. Technical SEO Standards

### Site Speed
- Use WebP for all images (with JPEG fallback)
- Compress all images (max file size: 200KB for hero, 100KB for inline)
- Preload hero image and heading font
- Defer all non-critical JavaScript
- Inline critical CSS

### Crawlability
- XML sitemap: auto-generated, submitted to Google Search Console
- `robots.txt`: allow all except `/admin/`, `/thank-you/` (no-index via meta)
- Canonical tags on every page (including paginated pages)
- No duplicate content (no `?page=1` style canonical issues)
- Redirect all `www` → non-`www` (or vice versa, consistently)
- HTTPS enforced sitewide

### Structured Data
- No schema errors in Google's Rich Results Test
- FAQPage schema: max 2 pages per site using it
- LocalBusiness schema on every city page
- BreadcrumbList on all pages except homepage

---

## 7. Page Speed Protocol

```
Image optimization:    hero ≤ 200KB WebP, inline ≤ 100KB WebP
Font loading:          preload WOFF2, font-display: swap
CSS:                   critical CSS inlined, rest deferred
JavaScript:            defer all non-critical, no render-blocking scripts
Caching:               static assets cached 1 year, HTML cached 24 hours
CDN:                   all static assets served via CDN
```

---

## 8. SEO Monitoring KPIs

Track these metrics weekly in Google Search Console + Analytics:

| Metric | Target |
|--------|--------|
| Organic impressions | Growing month-over-month |
| Average position | < 20 for primary keywords within 90 days |
| Click-through rate | > 3% for informational, > 5% for commercial |
| Core Web Vitals | All pages in "Good" category |
| Index coverage | 0 pages with errors |
| Backlinks | Growing from relevant domains |

---

*Parent: [FRAMEWORK.md](../FRAMEWORK.md) | See also: [keyword-strategy.md](./keyword-strategy.md) | [internal-linking.md](./internal-linking.md) | [schema-templates.md](./schema-templates.md)*
