# Section Template

Use this template when creating a **new custom section**. All sections in `_sections/` follow this structure.

---

## Section Front Matter

```yaml
---
section_id: "unique-section-id"
section_name: "Human-Readable Section Name"
section_type: "hero|features|testimonials|faq|cta|contact|custom"
schema_type: ""           # Leave empty if no schema, else e.g. "FAQPage"
available_variants:
  - default
  - minimal
  - full
  - dark
  - light
variables:
  - "{headline}"
  - "{subheadline}"
  - "{body_copy}"
  - "{cta_text}"
  - "{cta_url}"
---
```

---

## Section Body Template

```markdown
<!-- ============================================================
     SECTION: {section_name}
     Variants: default | minimal | full | dark | light
     Schema: {schema_type or "none"}
     ============================================================ -->

## {headline}

{subheadline — one sentence supporting the headline}

{body_copy — 2–4 sentences. Apply PAS or BAB framework.}

[{cta_text}]({cta_url}){.btn .btn-primary}
```

---

## Schema Block (if applicable)

Append the schema block after the section content. The schema block is injected into `<head>` at render time.

```json
{
  "@context": "https://schema.org",
  "@type": "{schema_type}",
  "name": "{section_name}",
  "description": "{body_copy_first_sentence}"
}
```

---

## Section Composition Guidelines

| Rule | Description |
|------|-------------|
| **One job per section** | Each section does one thing. Hero sells the click; Services explain the offer; Testimonials build trust. |
| **One primary CTA per section** | Never have two competing CTAs in the same section. |
| **Mobile-first layout** | Stack columns vertically on mobile. All content must be legible at 375px width. |
| **Contrast ratio** | Text vs. background must be ≥ 4.5:1 (WCAG AA). |
| **Image alt text** | Every `<img>` must have a descriptive, keyword-aware `alt` attribute. |
| **Loading** | Above-fold images: `loading="eager"`. Below-fold images: `loading="lazy"`. |

---

## Variant Definitions

| Variant | Use Case | Differences |
|---------|----------|------------|
| `default` | Standard mid-page placement | Full layout with image, headline, body, CTA |
| `minimal` | Inline CTA repeat | Headline + CTA button only, no image |
| `full` | Bottom-of-page primary CTA | Large, high-contrast, full-width layout |
| `dark` | Contrast section | Dark background, light text |
| `light` | Standard contrast | Light background, dark text |

---

*Parent: [FRAMEWORK.md](../FRAMEWORK.md) | See also: [page-template.md](./page-template.md)*
