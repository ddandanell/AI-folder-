# Authority Blog: Structure

---

## Folder Structure

```
project-root/
├── _config/
│   ├── project-config.md
│   └── global-settings.md
│
├── pages/
│   ├── index.md                          ← Homepage (brand + niche hub)
│   ├── about/
│   │   └── index.md
│   ├── contact/
│   │   └── index.md
│   ├── newsletter/
│   │   └── index.md                      ← Email opt-in page
│   │
│   ├── {pillar-1}/
│   │   └── index.md                      ← Pillar 1 (hub page)
│   ├── {pillar-2}/
│   │   └── index.md                      ← Pillar 2 (hub page)
│   │
│   ├── blog/
│   │   ├── index.md                      ← Blog index (paginated)
│   │   ├── {post-slug-1}/
│   │   │   └── index.md                  ← Blog Post
│   │   ├── {post-slug-2}/
│   │   │   └── index.md
│   │   └── ...
│   │
│   └── resources/
│       ├── index.md                      ← Resources hub
│       └── {resource-slug}/
│           └── index.md                  ← Individual resource
│
├── images/
│   ├── og/
│   ├── hero/
│   ├── blog/                             ← Featured images for posts
│   └── authors/                          ← Author headshots
│
├── authors/                              ← Author profile files
│   └── {author-slug}.md
│
└── fonts/
```

---

## Page Inventory

| Page | URL | Index? | Level | Priority |
|------|-----|--------|-------|---------|
| Homepage | `/` | Yes | 0 | 1.0 |
| Pillar 1 | `/{pillar-1}/` | Yes | 1 | 0.9 |
| Pillar 2 | `/{pillar-2}/` | Yes | 1 | 0.9 |
| Blog Index | `/blog/` | Yes | 1 | 0.8 |
| Blog Post | `/blog/{slug}/` | Yes | 2 | 0.7 |
| Blog Index p2 | `/blog/page/2/` | **No** (canonical → `/blog/`) | — | — |
| Resources Hub | `/resources/` | Yes | 1 | 0.7 |
| Resource | `/resources/{slug}/` | Yes | 2 | 0.6 |
| Newsletter | `/newsletter/` | Yes | 1 | 0.5 |
| About | `/about/` | Yes | 1 | 0.6 |

---

## Navigation Structure

```
Header:
  Logo | [Topics ▾] | [Blog] | [Resources] | [About] | [Newsletter button]

Topics Dropdown:
  {pillar-1} | {pillar-2} | {pillar-3}

Footer:
  Column 1: Topics (pillar links)
  Column 2: Recent Posts (latest 5)
  Column 3: Resources
  Column 4: Newsletter signup + social links
```

---

## Author Profile Template

```yaml
---
author_id: "{author-slug}"
name: "{Full Name}"
title: "{Job Title or Credential}"
bio: "{2–3 sentences: expertise, background, why they write for this site.}"
photo: "/images/authors/{author-slug}.jpg"
social:
  twitter: "https://twitter.com/{handle}"
  linkedin: "https://linkedin.com/in/{handle}"
expertise:
  - "{Topic 1}"
  - "{Topic 2}"
---
```

---

*Parent: [README.md](./README.md) | Pages: [pillar-page.md](./pages/pillar-page.md) | [blog-post.md](./pages/blog-post.md)*
