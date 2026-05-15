# Service Business: Structure

Complete file and folder structure for a Service Business project type.

---

## Folder Structure

```
project-root/
├── _config/
│   ├── project-config.md
│   └── global-settings.md
│
├── pages/
│   ├── index.md                           ← Homepage
│   ├── about/
│   │   └── index.md                       ← About page
│   ├── services/
│   │   ├── index.md                       ← Services overview (optional)
│   │   ├── {service-1}/
│   │   │   └── index.md                   ← Service 1 Pillar
│   │   ├── {service-2}/
│   │   │   └── index.md                   ← Service 2 Pillar
│   │   └── {service-3}/
│   │       └── index.md                   ← Service 3 Pillar
│   ├── blog/
│   │   ├── index.md                       ← Blog listing page
│   │   ├── {post-slug-1}/
│   │   │   └── index.md                   ← Blog Post 1
│   │   └── {post-slug-2}/
│   │       └── index.md                   ← Blog Post 2
│   ├── faq/
│   │   └── index.md                       ← Comprehensive FAQ
│   ├── contact/
│   │   └── index.md                       ← Contact page
│   ├── thank-you/
│   │   └── index.md                       ← Post-conversion (no-index)
│   ├── privacy/
│   │   └── index.md
│   └── terms/
│       └── index.md
│
├── images/
│   ├── og/                                ← 1200×630 OG images per page
│   ├── hero/                              ← Hero images (WebP)
│   ├── services/                          ← Service card images
│   ├── about/                             ← Team photos
│   └── testimonials/                      ← Reviewer photos (optional)
│
└── fonts/
```

---

## Page Inventory

| Page | URL | Index? | Level | Priority |
|------|-----|--------|-------|---------|
| Homepage | `/` | Yes | 0 | 1.0 |
| Services Hub | `/services/` | Yes | 1 | 0.8 |
| Service 1 | `/{service-1}/` | Yes | 1 | 0.9 |
| Service 2 | `/{service-2}/` | Yes | 1 | 0.9 |
| Service 3 | `/{service-3}/` | Yes | 1 | 0.9 |
| About | `/about/` | Yes | 1 | 0.7 |
| Blog Index | `/blog/` | Yes | 1 | 0.7 |
| Blog Post N | `/blog/{slug}/` | Yes | 2 | 0.6 |
| FAQ | `/faq/` | Yes | 1 | 0.8 |
| Contact | `/contact/` | Yes | 1 | 0.9 |
| Thank You | `/thank-you/` | **No** | — | — |
| Privacy | `/privacy/` | Yes | — | 0.1 |
| Terms | `/terms/` | Yes | — | 0.1 |

---

## Navigation Structure

```
Header Primary Nav:
  [Services ▾] [About] [Blog] [FAQ] [Contact] [CALL NOW button]

Services dropdown:
  {service-1} | {service-2} | {service-3}

Footer:
  Column 1: Services (list all)
  Column 2: Company (About, Blog, FAQ)
  Column 3: Contact (address, phone, hours)
  Column 4: Service Areas (top cities if applicable)
```

---

## Sitemap Priority

```xml
<url><loc>{domain}/</loc><priority>1.0</priority></url>
<url><loc>{domain}/{service-1}/</loc><priority>0.9</priority></url>
<url><loc>{domain}/{service-2}/</loc><priority>0.9</priority></url>
<url><loc>{domain}/faq/</loc><priority>0.8</priority></url>
<url><loc>{domain}/about/</loc><priority>0.7</priority></url>
<url><loc>{domain}/blog/{slug}/</loc><priority>0.6</priority></url>
```

---

*Parent: [README.md](./README.md) | Pages: [pages/](./pages/)*
