# Project Type 02: Service Business

**Best for:** Local or national service companies with multiple services, ongoing lead generation, and multi-page SEO strategy.

**Goal:** Rank for multiple service + location keywords; generate consistent inbound leads from organic search.

---

## When to Use This Type

- You offer multiple services (2–10+)
- You want organic search to be a primary lead source
- You serve a city or region (not just online)
- You want to grow your web presence over time without rebuilding

---

## Page Structure

```
/ (Homepage)
├── /services/                    ← Services overview (optional hub)
│   ├── /{service-1}/             ← Service Pillar Page
│   ├── /{service-2}/
│   └── /{service-3}/
├── /about/                       ← Brand story, team, credentials
├── /blog/                        ← Content marketing (optional)
│   └── /blog/{post-slug}/
├── /faq/                         ← Comprehensive FAQ
├── /contact/                     ← Lead capture
├── /thank-you/                   ← Post-conversion (no-index)
├── /privacy/
└── /terms/
```

---

## Section Order by Page Type

### Homepage
```
1. Hero (brand + primary service + city)
2. Services (all services, card grid)
3. About (trust + credentials)
4. Testimonials
5. CTA (full)
6. FAQ (top 5 questions)
7. Contact
```

### Service Pillar Page
```
1. Hero (service-specific)
2. About (service-focused)
3. Related Services
4. Testimonials (service-filtered)
5. CTA (minimal — mid-page)
6. FAQ (service-specific)
7. CTA (full)
8. Contact
```

---

## SEO Strategy

- **Homepage**: Targets "{primary service} {city}" — T1 keyword
- **Service pages**: Target "{specific service} {city}" — T2 keyword each
- **Blog posts**: Target informational T3/T4 keywords, link back to service pages
- **FAQ page**: Targets long-tail question keywords

Internal linking follows hub-and-spoke:
- Homepage → all service pages
- All service pages → homepage + related services
- Blog posts → most relevant service page

---

## Files in This Project Type

- [`structure.md`](./structure.md) — Detailed file/folder structure
- [`pages/homepage.md`](./pages/homepage.md) — Homepage template
- [`pages/service-page.md`](./pages/service-page.md) — Service pillar template
- [`pages/about.md`](./pages/about.md) — About page template
- [`pages/blog-post.md`](./pages/blog-post.md) — Blog post template

---

## Config Overrides

```yaml
project_type: "service-business"
blog_enabled: true
auto_generate_city_pages: false    # Enable if serving multiple cities
auto_generate_service_pages: true
cta_form_enabled: true
cta_phone_enabled: true
```

---

*Parent: [README.md](../../README.md) | Previous: [01-landing-page](../01-landing-page/README.md) | Next: [03-local-seo](../03-local-seo/README.md)*
