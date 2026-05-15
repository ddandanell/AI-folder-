# About Section

**Section ID:** `about`
**Schema:** `Organization` or `LocalBusiness`
**Variants:** `default` | `split-image` | `timeline` | `stats-bar`

---

## Purpose

The About section builds **trust and credibility**. At this point in the page, the visitor knows what you do (Hero + Services). Now they need to believe *you specifically* are the right choice. This section answers: "Why should I trust you?"

---

## Variables

```yaml
about_section:
  headline: "Why {City} Trusts {Brand Name}"
  subheadline: "{Years} years of {service category} excellence."
  body: |
    {2–3 paragraphs establishing authority, story, and proof}
  stats:
    - value: "{N}+"
      label: "Projects Completed"
    - value: "{N}+"
      label: "5-Star Reviews"
    - value: "{N}"
      label: "Years in Business"
    - value: "{N}%"
      label: "Customer Satisfaction"
  image_url: "/images/about/team.webp"
  image_alt: "{Brand} team — {City} {service}"
  certifications:
    - name: "Licensed Contractor"
      logo: "/images/certs/licensed.svg"
    - name: "BBB Accredited"
      logo: "/images/certs/bbb.svg"
    - name: "Google Guaranteed"
      logo: "/images/certs/google-guaranteed.svg"
  cta_text: "Meet the Team"
  cta_url: "/about/"
```

---

## Content Framework

Apply **BAB (Before → After → Bridge)** or storytelling:

```
BEFORE   = The problem your customers faced before finding you
AFTER    = The transformation / outcome you deliver
BRIDGE   = How YOU specifically make that happen
```

---

## Copy Example

```markdown
## Why {City} Trusts {Brand}

For over {N} years, {Brand} has been the go-to {service} company for homeowners and businesses across {Region}. We started because we were tired of seeing people overpay for poor-quality work — so we built the company we'd want to hire ourselves.

Every job we take on is backed by our **100% satisfaction guarantee**: if you're not completely happy, we'll make it right at no extra charge. That's not a marketing line — it's how we've earned {N}+ five-star reviews.

**{N}+ Projects Completed · {N}+ 5-Star Reviews · {N} Years in Business**

We're fully licensed, bonded, and insured. Our technicians are background-checked and trained to the highest industry standards.

[Get to Know Our Team](/about/){.btn .btn-secondary}
```

---

## Rules

- Stats must be real and verifiable — no fabricated numbers
- Certifications must be current and genuine
- Body copy should mention the primary city/region naturally
- If a founding story exists, include it — authenticity converts
- Photo of the team or owner significantly increases trust

---

*Parent: [section-template.md](../_templates/section-template.md) | Used by: [page-template.md](../_templates/page-template.md)*
