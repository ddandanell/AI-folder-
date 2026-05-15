# Global Settings

Framework-level defaults that apply across ALL project types. Override specific values in `project-config.md`.

---

## Page Generation Defaults

```yaml
default_robots: "index, follow"
default_og_type: "website"
default_schema_context: "https://schema.org"
max_title_length: 60
max_description_length: 160
canonical_trailing_slash: false
sitemap_changefreq_homepage: "daily"
sitemap_changefreq_pillar: "weekly"
sitemap_changefreq_city: "weekly"
sitemap_changefreq_blog: "monthly"
sitemap_priority_homepage: 1.0
sitemap_priority_pillar: 0.9
sitemap_priority_city: 0.8
sitemap_priority_blog: 0.7
sitemap_priority_supporting: 0.5
```

---

## Internal Linking Defaults

```yaml
max_internal_links_per_page: 20
min_internal_links_per_page: 5
anchor_text_exact_match_pct: 30
anchor_text_partial_match_pct: 40
anchor_text_generic_pct: 30
max_click_depth_from_home: 3
hub_spoke_enabled: true
geographic_cluster_enabled: true
topic_cluster_enabled: true
```

---

## Section Order Defaults

```yaml
default_section_order:
  - hero
  - services
  - about
  - testimonials
  - faq
  - cta
  - contact
cta_repeat_after_sections:
  - services
  - testimonials
```

---

## Image Standards

```yaml
og_image_width: 1200
og_image_height: 630
og_image_format: "jpg"
hero_image_format: "webp"
hero_image_max_width: 1920
logo_format: "svg"
```

---

## Performance Standards

```yaml
target_lcp_seconds: 2.5
target_fid_ms: 100
target_cls: 0.1
lazy_load_images: true
preload_hero_image: true
defer_non_critical_js: true
minify_html: true
minify_css: true
minify_js: true
```

---

## Accessibility Standards

```yaml
wcag_level: "AA"
alt_text_required: true
aria_labels_required: true
color_contrast_min_ratio: 4.5
keyboard_navigation: true
```

---

## Naming Conventions

```yaml
slug_separator: "-"
slug_lowercase: true
slug_remove_stopwords: true
slug_stopwords:
  - "the"
  - "a"
  - "an"
  - "of"
  - "in"
  - "at"
  - "for"
  - "to"
image_naming: "{page-slug}-{section}-{index}.{ext}"
file_naming: "{type}-{slug}.md"
```

---

## Supported Output Formats

```yaml
supported_outputs:
  - static-html         # Pure HTML output
  - nextjs              # Next.js / React
  - nuxtjs              # Nuxt.js / Vue
  - astro               # Astro framework
  - wordpress           # WordPress theme/ACF
  - webflow             # Webflow CMS
  - markdown-only       # MD files only (no rendering)
```

---

*Parent: [project-config.md](./project-config.md) | Return: [FRAMEWORK.md](../FRAMEWORK.md)*
