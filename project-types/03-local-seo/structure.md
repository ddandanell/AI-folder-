# Local SEO: Structure

---

## Folder Structure

```
project-root/
├── _config/
│   ├── project-config.md         ← Fill cities[] and services[]
│   └── global-settings.md
│
├── pages/
│   ├── index.md                  ← Homepage (primary city + service)
│   ├── service-area/
│   │   └── index.md              ← Service area overview
│   ├── about/
│   │   └── index.md
│   ├── faq/
│   │   └── index.md
│   ├── contact/
│   │   └── index.md
│   ├── thank-you/
│   │   └── index.md              ← no-index
│   │
│   ├── {service-1}/
│   │   ├── index.md              ← Service 1 Pillar
│   │   ├── {city-1}/
│   │   │   └── index.md          ← Service 1 × City 1
│   │   ├── {city-2}/
│   │   │   └── index.md          ← Service 1 × City 2
│   │   └── {city-3}/
│   │       └── index.md
│   │
│   └── {service-2}/
│       ├── index.md
│       ├── {city-1}/
│       │   └── index.md
│       └── {city-2}/
│           └── index.md
│
└── images/
    ├── og/
    ├── hero/
    ├── services/
    └── cities/                   ← City-specific images (optional)
```

---

## Page Inventory (Auto-Generated)

| Page | URL | Index? | Level | Priority |
|------|-----|--------|-------|---------|
| Homepage | `/` | Yes | 0 | 1.0 |
| Service Area | `/service-area/` | Yes | 1 | 0.8 |
| Service 1 Pillar | `/{service-1}/` | Yes | 1 | 0.9 |
| City Page (S1×C1) | `/{service-1}/{city-1}/` | Yes | 2 | 0.8 |
| City Page (S1×C2) | `/{service-1}/{city-2}/` | Yes | 2 | 0.8 |
| FAQ | `/faq/` | Yes | 1 | 0.8 |
| Contact | `/contact/` | Yes | 1 | 0.9 |

**Total pages for 3 services × 10 cities = 30 city pages + 3 pillars + homepage = 34+ pages**

---

## Navigation Structure

```
Header:
  Logo | [Services ▾] | [Service Area] | [About] | [FAQ] | [☎ Call Now]

Services Dropdown:
  {service-1} | {service-2} | {service-3}

Footer:
  Column 1: Services
  Column 2: Service Areas (city list)
  Column 3: Company (About, Blog, FAQ)
  Column 4: Contact + Hours + Map
```

---

## Cross-Linking Map (City Pages)

Each city page cross-links to:
1. Its parent service pillar page (UP)
2. 3 geographically nearest city pages for the same service (ACROSS)
3. Same city's pages for other services (DIAGONAL, 1–2 links max)

```
/plumbing/austin/ links to:
  ↑ /plumbing/ (parent pillar)
  ↔ /plumbing/round-rock/ (nearby city)
  ↔ /plumbing/cedar-park/ (nearby city)
  ↔ /plumbing/pflugerville/ (nearby city)
  → /drain-cleaning/austin/ (same city, different service — 1 link)
```

---

*Parent: [README.md](./README.md) | Pages: [city-page.md](./pages/city-page.md)*
