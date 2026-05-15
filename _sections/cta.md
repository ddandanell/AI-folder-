# CTA Section

**Section ID:** `cta`
**Schema:** None
**Variants:** `full` | `minimal` | `banner` | `split` | `floating-bar`

---

## Purpose

The CTA (Call to Action) section exists to **convert interest into contact**. It appears at minimum at the bottom of every page, and after high-intent sections (Services, Testimonials). Its job is to remove friction and give the visitor a clear, confident next step.

---

## Variables

```yaml
cta_section:
  variant: "full"         # full | minimal | banner | split | floating-bar
  headline: "{Action-oriented promise headline}"
  subheadline: "{Reinforce urgency or guarantee — 1 sentence}"
  cta_primary_text: "Get Your Free Quote"
  cta_primary_url: "#contact"
  cta_secondary_text: "Call {phone}"
  cta_secondary_url: "tel:{phone_digits}"
  guarantee_text: "100% satisfaction guaranteed or we make it right — at no charge."
  urgency_badge: "Same-Day Availability"
  background_color: "primary"   # primary | dark | light | accent
```

---

## Variant Definitions

### `full` — Primary Bottom-of-Page CTA

Large, high-contrast section. Full width. Two CTAs (form + phone). Used at the bottom of every page before the Contact section.

```markdown
---

## Ready to Get Started? {City}'s Trusted {Service} Team Is Standing By.

Same-day appointments available. No hidden fees. 100% satisfaction guaranteed.

[Get a Free Quote](#contact){.btn .btn-primary .btn-large}  [Call {phone}](tel:{phone}){.btn .btn-outline .btn-large}

✅ Licensed & Insured  ·  ✅ Background-Checked Technicians  ·  ✅ Satisfaction Guaranteed

---
```

### `minimal` — Mid-Page Inline CTA

Single line, one CTA button. Used between sections to catch visitors ready to convert early.

```markdown
> Ready to book? [Get a free quote](#contact) — it takes under 2 minutes.
```

### `banner` — Sticky Top/Bottom Bar

A thin persistent bar that appears on scroll. Contains phone number and one CTA.

```markdown
<!-- Floating bar (rendered via JS) -->
{phone} — Same-Day Service Available → [Book Now](#contact)
```

---

## Copy Frameworks

### Urgency-Based
```
Headline: "Don't wait — {problem} gets worse fast."
Sub: "Book your free inspection today and get same-day availability."
```

### Guarantee-Based
```
Headline: "100% Satisfaction — Guaranteed."
Sub: "If you're not happy with the work, we'll fix it at no extra cost. Zero risk."
```

### Social Proof-Based
```
Headline: "Join {N}+ happy customers in {city}."
Sub: "Rated 4.9/5 on Google. See why {city} trusts {brand}."
```

### Scarcity-Based (use carefully — only if genuinely true)
```
Headline: "Only {N} spots left this week."
Sub: "We limit bookings to ensure quality. Reserve your spot now."
```

---

## Rules

- CTA button label must be **action-oriented** — start with a verb (Get, Book, Call, Request, Start)
- Never use "Submit" or "Click Here" as button text
- Always offer TWO paths: form-based (lower friction for research phase) AND phone (higher intent)
- Guarantee or trust signal must appear near (not just below) the primary CTA button
- `full` variant must be high-contrast — primary brand color background is recommended
- On mobile, phone CTA comes first (phone intent is higher on mobile)

---

## Placement Rules

```
Every page: 1× minimal (after Services) + 1× full (before Contact)
Long pages: 1× minimal every 400–600 words of body text
Floating bar: optional — enable in project-config.md
```

---

*Parent: [section-template.md](../_templates/section-template.md) | Used by: [page-template.md](../_templates/page-template.md)*
