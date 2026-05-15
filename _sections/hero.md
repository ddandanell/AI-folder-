# Hero Section

**Section ID:** `hero`
**Schema:** None (schema is page-level)
**Variants:** `default` | `split` | `centered` | `video-background` | `dark`

---

## Purpose

The Hero section is the **first impression**. Its only job is to:
1. Confirm the visitor is in the right place (keyword signal)
2. State the primary value proposition in one line
3. Provide an unmissable CTA

The Hero section must be visible **above the fold** on all devices.

---

## Variables

```yaml
hero:
  headline: "{Primary Keyword} — {Benefit Statement}"
  subheadline: "{One sentence: who you help + how + outcome}"
  cta_primary_text: "Get a Free Quote"
  cta_primary_url: "#contact"
  cta_secondary_text: "Call Now: {phone}"
  cta_secondary_url: "tel:{phone_digits}"
  image_url: "/images/hero/{page-slug}-hero.webp"
  image_alt: "{Primary keyword} — {brand name}"
  trust_badges:
    - "Licensed & Insured"
    - "5-Star Rated"
    - "Same-Day Service"
  background_variant: "light"   # light | dark | image | gradient
```

---

## Content Framework

Apply **AIDA** to hero copy:

```
HEADLINE    = Attention  — Bold keyword-rich promise
SUBHEADLINE = Interest   — Who + how + outcome
BADGE ROW   = Desire     — Trust signals (reviews, awards, guarantees)
CTA BUTTON  = Action     — Single, clear next step
```

---

## Copy Examples

### Default Variant (Service Business)

```markdown
# Expert {Service} in {City}

Trusted by {N}+ homeowners and businesses. Fast response, guaranteed work, fair pricing.

✅ Licensed & Insured  |  ✅ 5-Star Google Rating  |  ✅ Same-Day Available

[Get a Free Quote](#contact){.btn .btn-primary}  [Call Now: {phone}](tel:{phone}){.btn .btn-secondary}
```

### Centered Variant (Landing Page)

```markdown
# Stop {Pain Point} — Start {Desired Outcome}

{Brand} helps {target audience} {achieve result} without {common objection}.

[{Primary CTA}]({cta_url}){.btn .btn-primary .btn-large}

⭐⭐⭐⭐⭐ Rated 4.9/5 from {N} reviews
```

---

## Rules

- H1 must contain the primary keyword verbatim or near-verbatim
- CTA button must contrast ≥ 4.5:1 against its background
- Hero image must have descriptive `alt` text with primary keyword
- Trust badges must be factual — no fabricated claims
- Hero must load in < 2.5 seconds (LCP target)
- Secondary CTA is optional but recommended for phone-based businesses

---

*Parent: [section-template.md](../_templates/section-template.md) | Used by: [page-template.md](../_templates/page-template.md)*
