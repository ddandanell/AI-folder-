# Metadata Template

Defines the full metadata block injected into every page's `<head>`. Variables are sourced from each page's front matter and `_config/project-config.md`.

---

## Full Metadata Block

```html
<!-- ═══════════════════════════════════════════════
     PRIMARY META
     ═══════════════════════════════════════════════ -->
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>{title}</title>
<meta name="description" content="{description}">
<meta name="robots" content="{robots}">
<link rel="canonical" href="{canonical}">

<!-- ═══════════════════════════════════════════════
     OPEN GRAPH
     ═══════════════════════════════════════════════ -->
<meta property="og:type" content="{og_type}">
<meta property="og:title" content="{og_title}">
<meta property="og:description" content="{og_description}">
<meta property="og:image" content="{og_image}">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta property="og:url" content="{canonical}">
<meta property="og:site_name" content="{brand_name}">
<meta property="og:locale" content="{primary_language}_US">

<!-- ═══════════════════════════════════════════════
     TWITTER CARD
     ═══════════════════════════════════════════════ -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="{og_title}">
<meta name="twitter:description" content="{og_description}">
<meta name="twitter:image" content="{og_image}">

<!-- ═══════════════════════════════════════════════
     HREFLANG (multi-language only)
     ═══════════════════════════════════════════════ -->
<!-- <link rel="alternate" hreflang="en" href="{canonical}"> -->
<!-- <link rel="alternate" hreflang="es" href="{canonical_es}"> -->

<!-- ═══════════════════════════════════════════════
     PRELOADS
     ═══════════════════════════════════════════════ -->
<link rel="preload" as="image" href="{hero_image_url}">
<link rel="preload" as="font" href="/fonts/{heading_font}.woff2" crossorigin>

<!-- ═══════════════════════════════════════════════
     SCHEMA (JSON-LD — injected per page type)
     ═══════════════════════════════════════════════ -->
<script type="application/ld+json">
{schema_json}
</script>

<!-- ═══════════════════════════════════════════════
     ANALYTICS (injected from config)
     ═══════════════════════════════════════════════ -->
<!-- Google Tag Manager -->
<!-- Google Analytics -->
<!-- Facebook Pixel -->
```

---

## Title Tag Formulas by Page Type

| Page Type | Formula | Example |
|-----------|---------|---------|
| Homepage | `{Primary Keyword} \| {Brand}` | `Plumbing Services \| AcmePlumb` |
| Pillar/Service | `{Service} in {City} \| {Brand}` | `Drain Repair in Austin \| AcmePlumb` |
| City Page | `{Service} {City} - {Brand}` | `Plumbing Austin - AcmePlumb` |
| Keyword Page | `{Long-tail Keyword} \| {Brand}` | `Emergency Plumber Near Me \| AcmePlumb` |
| Blog Post | `{Article Title} - {Brand}` | `How to Fix a Leaky Faucet - AcmePlumb` |
| FAQ | `Frequently Asked Questions \| {Brand}` | `FAQ \| AcmePlumb` |

**Character limits:** Title ≤ 60 chars · Description ≤ 160 chars

---

## Meta Description Formulas by Page Type

| Page Type | Formula |
|-----------|---------|
| Homepage | `{Benefit statement}. {Secondary benefit}. {Soft CTA}.` |
| Service Page | `{Action verb} {service} in {city}. {USP}. {CTA}.` |
| City Page | `Looking for {service} in {city}? {Brand} {USP}. Call {phone} today.` |
| Blog Post | `{Summary of article in 1–2 sentences}. Read more.` |

---

## Breadcrumb Schema (BreadcrumbList)

Injected on all pages except the homepage:

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "{domain}"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "{parent_page_name}",
      "item": "{domain}{parent_page_slug}"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "{current_page_name}",
      "item": "{canonical}"
    }
  ]
}
```

---

*Parent: [FRAMEWORK.md](../FRAMEWORK.md) | See also: [_seo/schema-templates.md](../_seo/schema-templates.md)*
