# Contact Section

**Section ID:** `contact`
**Schema:** `ContactPage` + `LocalBusiness`
**Variants:** `form-only` | `form-map` | `form-info` | `minimal`

---

## Purpose

The Contact section is the **conversion endpoint** — where interest becomes a lead. It must remove every possible point of friction and reassure the visitor that they are making the right decision.

---

## Variables

```yaml
contact_section:
  headline: "Get in Touch"
  subheadline: "We respond within {N} minutes during business hours."
  layout: "form-info"      # form-only | form-map | form-info | minimal
  show_map: true
  show_hours: true
  show_phone: true
  show_email: false         # Hide email to prevent spam; use form instead
  form:
    fields:
      - id: "name"
        label: "Your Name"
        type: "text"
        required: true
        placeholder: "John Smith"
      - id: "phone"
        label: "Phone Number"
        type: "tel"
        required: true
        placeholder: "(555) 000-0000"
      - id: "service"
        label: "Service Needed"
        type: "select"
        required: true
        options: []          # Pulled from project-config.md → services[]
      - id: "message"
        label: "Additional Details"
        type: "textarea"
        required: false
        placeholder: "Describe your issue or project..."
    submit_text: "Request My Free Quote"
    success_message: "Thanks, {name}! We'll call you within {N} minutes."
    redirect_url: "/thank-you/"
  business_hours:
    - day: "Monday–Friday"
      hours: "7:00 AM – 7:00 PM"
    - day: "Saturday"
      hours: "8:00 AM – 5:00 PM"
    - day: "Sunday"
      hours: "Emergency Only"
```

---

## Content Example (Form + Info Layout)

```markdown
## Get in Touch

Fill out the form below and we'll get back to you within 15 minutes during business hours.

[FORM]

---

📍 {address.street}, {address.city}, {address.state} {address.zip}
📞 [{phone}](tel:{phone_digits})
🕐 Mon–Fri: 7 AM – 7 PM · Sat: 8 AM – 5 PM · Sun: Emergency Only

[VIEW ON GOOGLE MAPS →]({google_maps_url})
```

---

## Form Conversion Rules

1. **As few fields as possible** — Name, Phone, Service, Message (4 fields maximum for top-of-funnel)
2. **Phone before email** — phone leads convert higher; email is secondary
3. **Service dropdown** — pre-qualifies the lead and routes internally
4. **Submit button copy** — "Request My Free Quote" outperforms "Submit" by 35%+
5. **Success message** — must set expectations (callback time) and reinforce confidence
6. **Redirect to /thank-you/** — allows conversion tracking in Analytics/Pixel

---

## Trust Signals Near Form

Always display near the form (not just in the form section header):

```markdown
🔒 Your information is 100% private and never shared.
✅ No spam. No pressure. Cancel anytime.
⭐⭐⭐⭐⭐ 4.9/5 from {N} Google Reviews
```

---

## Schema Block

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "{brand_name}",
  "telephone": "{phone}",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "{address.street}",
    "addressLocality": "{address.city}",
    "addressRegion": "{address.state}",
    "postalCode": "{address.zip}",
    "addressCountry": "{address.country}"
  },
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday"],
      "opens": "07:00",
      "closes": "19:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Saturday"],
      "opens": "08:00",
      "closes": "17:00"
    }
  ]
}
```

---

## Rules

- Contact section is **always last** on every page (below FAQ, above Footer)
- On mobile, phone number must be a clickable `tel:` link
- Map embed must include the business pin marker
- If no physical address, use a service area map instead of a point map

---

*Parent: [section-template.md](../_templates/section-template.md) | Used by: [page-template.md](../_templates/page-template.md)*
