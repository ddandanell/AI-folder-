# AI-Folder: Scalable MD-File Digital Framework

A standardized, reusable Markdown-based system for automatically generating and controlling different types of websites and digital structures. Every project follows a predefined architecture, linking strategy, content structure, SEO logic, and conversion-focused layout system.

---

## What This Framework Does

- **Controls project structure** through MD files that act as a single source of truth
- **Generates pages dynamically** based on project type and configuration
- **Systematizes internal linking** so every page supports every other page
- **Interconnects SEO structures** across city pages, service pages, keyword pages, and content pages
- **Follows conversion psychology** in every section and layout decision
- **Scales automatically** — add a new city, service, or keyword by adding one MD file

---

## Supported Project Types

| # | Type | Best For |
|---|------|----------|
| 1 | [Landing Page](./project-types/01-landing-page/README.md) | Lead generation, product launches, single offers |
| 2 | [Service Business](./project-types/02-service-business/README.md) | Local/national service companies, agencies |
| 3 | [Local SEO](./project-types/03-local-seo/README.md) | Multi-location businesses, geographic targeting |
| 4 | [Authority / Blog](./project-types/04-authority-blog/README.md) | Content marketing, thought leadership, affiliate |
| 5 | [News / Content Platform](./project-types/05-news-content/README.md) | Media sites, aggregators, programmatic SEO |

---

## Repository Structure

```
AI-folder-/
├── README.md                    ← You are here
├── FRAMEWORK.md                 ← System architecture & philosophy
│
├── _config/                     ← Global & per-project configuration
│   ├── project-config.md
│   └── global-settings.md
│
├── _templates/                  ← Reusable page/section/metadata templates
│   ├── page-template.md
│   ├── section-template.md
│   └── metadata-template.md
│
├── _sections/                   ← Modular, swappable page sections
│   ├── hero.md
│   ├── services.md
│   ├── about.md
│   ├── testimonials.md
│   ├── faq.md
│   ├── cta.md
│   └── contact.md
│
├── _seo/                        ← SEO strategy, schemas, linking rules
│   ├── seo-framework.md
│   ├── schema-templates.md
│   ├── keyword-strategy.md
│   └── internal-linking.md
│
├── _automation/                 ← Page generation & linking automation
│   ├── page-generator.md
│   └── linking-rules.md
│
└── project-types/               ← Ready-to-deploy project blueprints
    ├── 01-landing-page/
    ├── 02-service-business/
    ├── 03-local-seo/
    ├── 04-authority-blog/
    └── 05-news-content/
```

---

## Quick Start

1. Choose a project type from `project-types/`
2. Copy the chosen folder to your project root
3. Fill in `_config/project-config.md` with your business data
4. Run the automation rules in `_automation/page-generator.md` to scaffold all pages
5. Customize sections from `_sections/` as needed
6. Apply the SEO framework from `_seo/seo-framework.md`

---

## Core Principles

1. **MD files are the source of truth** — never hard-code content in templates
2. **Every section is modular** — swap sections without rebuilding pages
3. **Every link is intentional** — follow `_seo/internal-linking.md` strictly
4. **Every page has a job** — defined by its position in the page hierarchy
5. **Automation over manual work** — if you're doing it twice, automate it

---

*See [FRAMEWORK.md](./FRAMEWORK.md) for the full system architecture documentation.*
