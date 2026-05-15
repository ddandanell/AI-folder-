# FAQ Section

**Section ID:** `faq`
**Schema:** `FAQPage` (required — always inject)
**Variants:** `accordion` | `two-column` | `list` | `card-grid`

---

## Purpose

The FAQ section serves two jobs simultaneously:
1. **Conversion** — handles objections and answers the questions that prevent people from contacting you
2. **SEO** — targets question-format long-tail keywords and qualifies for FAQ rich results in Google

---

## Variables

```yaml
faq_section:
  headline: "Frequently Asked Questions"
  subheadline: "Everything you need to know about our {service} services."
  layout: "accordion"      # accordion | two-column | list | card-grid
  show_schema: true
  faqs:
    - question: "{Question text — phrase as the user would type it}"
      answer: "{2–4 sentences. Direct answer first, then context. Use first person (we/our).}"
      category: "pricing|process|qualifications|location|timing"
```

---

## Question Categories & Examples

### Pricing Questions
```
- How much does {service} cost in {city}?
- Do you offer free quotes?
- Do you have any payment plans?
- Is the quote price the final price?
```

### Process Questions
```
- How long does {service} take?
- What happens after I contact you?
- Do I need to be home during the service?
- Will you clean up after the job?
```

### Qualification Questions
```
- Are you licensed and insured?
- How long have you been in business?
- Do your technicians have background checks?
- What warranties do you offer?
```

### Service Area Questions
```
- Do you serve {nearby city}?
- What areas do you cover?
- Do you charge extra for travel?
```

### Emergency / Timing Questions
```
- Do you offer emergency {service}?
- What are your hours?
- How fast can you respond?
```

---

## Copy Example (Accordion)

```markdown
## Frequently Asked Questions

### How much does {service} cost in {city}?

Pricing depends on the scope of work, but most jobs in {city} range from ${low} to ${high}. We provide free, no-obligation quotes before any work begins — so you always know exactly what you'll pay.

### How quickly can you respond?

We offer same-day service for most requests. For emergencies, our average response time is under 60 minutes in {city} and surrounding areas.

### Are you licensed and insured?

Yes. {Brand} is fully licensed, bonded, and insured in the state of {State}. License #XXXXXXX. We carry $2M in general liability insurance and workers' compensation for all our technicians.

### Do you guarantee your work?

Absolutely. Every job we complete comes with a {N}-month workmanship guarantee. If any issue arises from our work within that period, we'll return and fix it at no charge.

### Which areas do you serve?

We serve {city} and the surrounding {radius}-mile area, including {city2}, {city3}, and {city4}. [See our full service area map](/service-area/).
```

---

## Schema Block (FAQPage)

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "{question}",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "{answer}"
      }
    }
  ]
}
```

---

## Rules

- Minimum 5 FAQs per page; 8–10 is optimal for SEO
- Each question should naturally match a search query people type
- Answer every question directly in the first sentence — do not bury the answer
- Do not use FAQPage schema on more than 2 pages of the same site with identical Q&A
- FAQ schema requires that answers be concise — keep under 300 words each
- Link to relevant service or city pages within answers when natural

---

*Parent: [section-template.md](../_templates/section-template.md) | Used by: [page-template.md](../_templates/page-template.md)*
