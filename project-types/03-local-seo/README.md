# Project Type 03: Local SEO

**Best for:** Businesses serving multiple cities or geographic areas, targeting "near me" and city-specific keywords, competing in local search results.

**Goal:** Dominate local search for every service + city combination in the service area.

---

## When to Use This Type

- You physically serve customers in multiple cities or regions
- "Near me" and "{service} {city}" queries are your main opportunity
- You want to scale coverage without rebuilding for each city
- You have or want a Google Business Profile for each location

---

## Page Structure

```
/ (Homepage — targets primary city + primary service)
├── /{service-1}/                  ← Service Pillar (national/broad)
│   ├── /{service-1}/{city-1}/     ← City Sub-Page
│   ├── /{service-1}/{city-2}/
│   └── /{service-1}/{city-3}/
├── /{service-2}/
│   ├── /{service-2}/{city-1}/
│   └── /{service-2}/{city-2}/
├── /service-area/                 ← Service area overview + map
├── /about/
├── /blog/
├── /faq/
├── /contact/
└── /thank-you/
```

---

## City Page Generation

City pages are the engine of Local SEO. For every `service × city` combination:

```
Input:   services = [plumbing, drain-cleaning, leak-detection]
         cities   = [austin, dallas, houston, san-antonio]

Output:  12 city pages automatically generated:
         /plumbing/austin/
         /plumbing/dallas/
         /plumbing/houston/
         /plumbing/san-antonio/
         /drain-cleaning/austin/
         ... (and so on)
```

Enable this in config:
```yaml
auto_generate_city_pages: true
```

---

## City Page Differentiation

**Google penalizes thin, duplicate city pages.** Each city page must have unique content. Use these signals to differentiate:

| Signal | How to Include |
|--------|---------------|
| City name | In headline, body (2–3x), FAQ questions |
| Neighborhood names | "We serve Zilker, South Congress, East Austin..." |
| Local landmarks | "Near [landmark]" in directions/about |
| Local testimonials | Filter by reviewer's city |
| City-specific FAQ | "How much does {service} cost in {city}?" |
| Nearby city links | "Also serving {city2}, {city3}..." |

---

## SEO Strategy

```
Homepage:         "{primary service} {primary city}" — T1
Service Pillar:   "{service}" (broad) — T1/T2
City Page:        "{service} {city}" — T2
City Sub-Page:    "{service} {neighborhood}" — T3
FAQ Page:         Question-format keywords — T3/T4
Blog Posts:       Informational — T3/T4
```

---

## Google Business Profile Integration

For local SEO, the GBP (Google Business Profile) must be consistent with the website:

```yaml
gbp_requirements:
  - NAP consistent: name, address, phone match website exactly
  - Primary category: matches {primary_service}
  - Website URL: matches {domain}
  - Photos: 10+ updated photos
  - Posts: minimum 1 per week
  - Reviews: actively requesting and responding
```

---

## Files in This Project Type

- [`structure.md`](./structure.md) — Detailed file/folder structure
- [`pages/city-page.md`](./pages/city-page.md) — City page template
- [`pages/service-area.md`](./pages/service-area.md) — Service area overview page

---

## Config Overrides

```yaml
project_type: "local-seo"
blog_enabled: true
auto_generate_city_pages: true
auto_generate_service_pages: true
cta_phone_enabled: true
cta_form_enabled: true
service_area_radius_km: 80
```

---

*Parent: [README.md](../../README.md) | Previous: [02-service-business](../02-service-business/README.md) | Next: [04-authority-blog](../04-authority-blog/README.md)*
