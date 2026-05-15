# Project Configuration

This file is the **single source of truth** for a project. All page generators, metadata templates, and linking rules read from this file. Fill in every field before generating pages.

---

## Business Identity

```yaml
project_name: "Your Business Name"
project_type: "service-business"       # landing-page | service-business | local-seo | authority-blog | news-content
domain: "https://yourdomain.com"
brand_name: "Your Brand"
tagline: "Your short brand promise"
primary_language: "en"
```

---

## Contact & Location

```yaml
phone: "+1 (555) 000-0000"
email: "contact@yourdomain.com"
address:
  street: "123 Main Street"
  city: "Your City"
  state: "ST"
  zip: "00000"
  country: "US"
google_maps_url: "https://maps.google.com/?cid=YOUR_CID"
```

---

## Primary SEO Targets

```yaml
primary_keyword: "your primary service keyword"
secondary_keywords:
  - "secondary keyword 1"
  - "secondary keyword 2"
  - "secondary keyword 3"
primary_city: "Your Primary City"
service_area_radius_km: 50
```

---

## Services

```yaml
services:
  - slug: "service-one"
    name: "Service One"
    short_description: "One sentence describing Service One."
    icon: "icon-service-one"
  - slug: "service-two"
    name: "Service Two"
    short_description: "One sentence describing Service Two."
    icon: "icon-service-two"
  - slug: "service-three"
    name: "Service Three"
    short_description: "One sentence describing Service Three."
    icon: "icon-service-three"
```

---

## Service Cities (Local SEO)

```yaml
cities:
  - slug: "city-one"
    name: "City One"
    state: "ST"
    lat: 00.0000
    lng: -00.0000
  - slug: "city-two"
    name: "City Two"
    state: "ST"
    lat: 00.0000
    lng: -00.0000
```

---

## Branding & Design

```yaml
colors:
  primary: "#0055FF"
  secondary: "#FF5500"
  background: "#FFFFFF"
  text: "#111111"
fonts:
  heading: "Inter"
  body: "Inter"
logo:
  light: "/images/logo-light.svg"
  dark: "/images/logo-dark.svg"
og_default_image: "/images/og/default.jpg"
```

---

## Social Media

```yaml
social:
  facebook: "https://facebook.com/yourpage"
  instagram: "https://instagram.com/yourhandle"
  linkedin: "https://linkedin.com/company/yourcompany"
  twitter: "https://twitter.com/yourhandle"
  youtube: ""
  tiktok: ""
```

---

## Analytics & Tracking

```yaml
google_analytics_id: "G-XXXXXXXXXX"
google_tag_manager_id: "GTM-XXXXXXX"
google_search_console_verification: ""
facebook_pixel_id: ""
hotjar_id: ""
```

---

## Content Settings

```yaml
blog_enabled: true
blog_posts_per_page: 12
faq_enabled: true
testimonials_count: 6
cta_phone_enabled: true
cta_form_enabled: true
```

---

## Automation Settings

```yaml
auto_generate_city_pages: true
auto_generate_service_pages: true
auto_generate_keyword_pages: false
auto_internal_linking: true
sitemap_auto_generate: true
schema_auto_inject: true
```

---

*Parent: [FRAMEWORK.md](../FRAMEWORK.md) | Next: [global-settings.md](./global-settings.md)*
