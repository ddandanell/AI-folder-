# Page Generator

Defines the rules and procedures for automatically generating all pages in a project from the configuration in `_config/project-config.md`.

---

## How Page Generation Works

```
Read project-config.md
       │
       ├─► Generate 1× Homepage
       ├─► Generate N× Service Pillar pages (from services[])
       ├─► Generate N× City pages (from cities[] × services[])
       ├─► Generate N× Keyword pages (from keyword_targets[])
       ├─► Generate 1× FAQ page
       ├─► Generate 1× Contact page
       └─► Generate 1× Thank You page
```

Each generated page is a Markdown file that:
1. Fills in the page front matter from config variables
2. References the correct section components
3. Is placed at the correct URL path

---

## Generation Rules by Page Type

### Homepage

```yaml
generated_file: "pages/index.md"
url: "/"
title_formula: "{primary_keyword} | {brand_name}"
sections:
  - hero
  - services (show all services)
  - about
  - testimonials
  - cta (full)
  - faq (top 5 questions)
  - contact
schema:
  - Organization
  - WebSite
  - LocalBusiness
```

---

### Service Pillar Pages

Generated once per service in `services[]`:

```yaml
generated_file: "pages/services/{service.slug}/index.md"
url: "/{service.slug}/"
title_formula: "{service.name} in {primary_city} | {brand_name}"
sections:
  - hero (service-specific headline)
  - about (service-focused variant)
  - services (related services)
  - testimonials (filtered by service)
  - cta (minimal, mid-page)
  - faq (service-specific questions)
  - cta (full)
  - contact
schema:
  - Service
  - LocalBusiness
  - FAQPage
  - BreadcrumbList
child_pages: []     # Links to city sub-pages for this service
```

---

### City Pages

Generated for each combination of `services[] × cities[]`:

```yaml
generated_file: "pages/services/{service.slug}/{city.slug}/index.md"
url: "/{service.slug}/{city.slug}/"
title_formula: "{service.name} {city.name} | {brand_name}"
sections:
  - hero (city + service specific)
  - services (same service list)
  - about (mention city name)
  - testimonials (filtered by city if possible)
  - cta (full)
  - faq (city-specific questions)
  - contact (with city-specific map)
schema:
  - LocalBusiness (with city GeoCoordinates)
  - FAQPage
  - BreadcrumbList
parent_page: "/{service.slug}/"
cross_links:        # Nearby city pages (within radius)
  - "/{service.slug}/{nearby_city.slug}/"
```

---

### Keyword Pages

Generated from the `keyword_targets[]` list (when `auto_generate_keyword_pages: true`):

```yaml
generated_file: "pages/keywords/{keyword.slug}/index.md"
url: "/{keyword.slug}/"
title_formula: "{keyword.name} | {brand_name}"
sections:
  - hero (keyword-specific)
  - services
  - testimonials
  - cta (full)
  - faq
schema:
  - Service
  - FAQPage
  - BreadcrumbList
parent_page: "/{primary_service}/"
```

---

### Blog Posts

Each blog post is a manually created file using this template:

```yaml
generated_file: "pages/blog/{post.slug}/index.md"
url: "/blog/{post.slug}/"
title_formula: "{post.title} | {brand_name}"
sections:
  - hero (article headline variant)
  - body_content (custom per post)
  - related_posts
  - cta (inline, contextual)
  - cta (full, bottom)
schema:
  - Article
  - BreadcrumbList
parent_page: "/blog/"
```

---

### FAQ Page

One dedicated FAQ page compiling all FAQs from all services:

```yaml
generated_file: "pages/faq/index.md"
url: "/faq/"
title_formula: "Frequently Asked Questions | {brand_name}"
sections:
  - hero (faq-specific)
  - faq (all questions, organized by category)
  - cta (full)
  - contact
schema:
  - FAQPage
  - BreadcrumbList
parent_page: "/"
```

---

### Utility Pages

Auto-generated, no custom content needed:

| Page | URL | Notes |
|------|-----|-------|
| Contact | `/contact/` | Full contact form + map |
| Thank You | `/thank-you/` | Post-conversion, no-index |
| Privacy Policy | `/privacy/` | Legal — fill in manually |
| Terms of Service | `/terms/` | Legal — fill in manually |
| Sitemap | `/sitemap.xml` | Auto-generated |
| 404 | `/404` | Custom 404 page |

---

## File Naming Convention

```
{page-type}-{primary-keyword-slug}.md

Examples:
  homepage.md
  service-drain-cleaning.md
  city-drain-cleaning-austin.md
  blog-how-to-unclog-drain.md
  faq-plumbing.md
```

---

## Generation Checklist

Before running generation, confirm:

```
[ ] project-config.md is fully filled in
[ ] services[] has at least 1 entry
[ ] cities[] has at least 1 entry (if local-seo project type)
[ ] primary_keyword is defined
[ ] domain is defined and correct
[ ] All image paths referenced in config actually exist
```

After generation, verify:

```
[ ] All pages have unique title tags
[ ] All pages have unique meta descriptions
[ ] No two pages share the same primary_keyword
[ ] All internal links resolve to real pages
[ ] Sitemap.xml is updated
[ ] Schema validates in Google's Rich Results Test
```

---

*Parent: [FRAMEWORK.md](../FRAMEWORK.md) | See also: [linking-rules.md](./linking-rules.md)*
