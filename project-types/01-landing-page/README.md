# Project Type 01: Landing Page

**Best for:** Single-offer businesses, product launches, lead generation campaigns, paid traffic destinations.

**Goal:** One visitor action — fill the form or call.

---

## When to Use This Type

- You have a single, well-defined offer
- Traffic comes primarily from ads (Google Ads, Meta Ads)
- You want maximum conversion rate, not broad SEO
- No blog or multi-page content strategy needed

---

## Page Structure

```
/ (Homepage = Landing Page)
├── /thank-you/          ← Post-conversion, no-index
└── /privacy/            ← Legal requirement for ad compliance
```

Landing pages typically have **no navigation** (or minimal nav) to eliminate distraction and maximize conversion.

---

## Section Order (Conversion-Optimized)

```
1. Hero          — Bold promise + primary CTA above fold
2. Problem       — Name the pain (PAS: Problem-Agitation-Solution)
3. Solution      — How your offer solves it
4. Features/     — What you get (3–5 bullet-style cards)
   Benefits
5. Social Proof  — Testimonials or logos
6. CTA (full)    — High-contrast CTA block
7. FAQ           — Handle remaining objections
8. Final CTA     — Last chance, urgency-based
9. Footer        — Minimal: Privacy Policy link only
```

---

## Conversion Psychology Stack

```
Hook (Hero)             → Grabs attention with the exact pain or desire
Problem Amplification   → "If this sounds familiar, you're not alone…"
Proof of Solution       → "Here's what changed for 500+ customers…"
Offer Reveal            → "Here's exactly what you get…"
Risk Reversal           → "If you're not happy, you pay nothing."
Urgency/Scarcity        → "Offer expires [date] / only [N] spots left"
Final CTA               → Simplest possible next step
```

---

## SEO Considerations

Landing pages are typically **not** the primary SEO strategy. However:

- Title tag should still target a keyword (e.g., for Quality Score in Google Ads)
- Meta description should be conversion-focused
- Page speed is critical (every 1 second delay = ~7% conversion loss)
- Schema: `Product`, `Offer`, or `Service` + optionally `FAQPage`

---

## Files in This Project Type

- [`structure.md`](./structure.md) — Detailed file/folder structure
- [`pages/landing-page.md`](./pages/landing-page.md) — Complete landing page template

---

## Config Overrides for Landing Pages

In `_config/project-config.md`, set:

```yaml
project_type: "landing-page"
blog_enabled: false
auto_generate_city_pages: false
auto_generate_service_pages: false
cta_form_enabled: true
cta_phone_enabled: true
```

---

*Parent: [README.md](../../README.md) | Next Project Type: [02-service-business](../02-service-business/README.md)*
