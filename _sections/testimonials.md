# Testimonials Section

**Section ID:** `testimonials`
**Schema:** `Review` + `AggregateRating`
**Variants:** `cards` | `carousel` | `masonry` | `single-featured` | `video`

---

## Purpose

Testimonials provide **social proof** — the psychological principle that people follow the actions and opinions of others. At this stage of the page, the visitor knows what you do and why you're credible. Now they need to see that *real people like them* have had a positive experience.

---

## Variables

```yaml
testimonials_section:
  headline: "What Our Customers Say"
  subheadline: "Real reviews from real customers in {City} and surrounding areas."
  layout: "cards"         # cards | carousel | masonry | single-featured | video
  show_aggregate_rating: true
  aggregate_rating:
    rating_value: "4.9"
    review_count: "{N}"
    rating_source: "Google"
  testimonials:
    - author_name: "{Full Name}"
      author_city: "{City, ST}"
      rating: 5
      review_date: "YYYY-MM-DD"
      review_text: "{2–4 sentences. Include specific detail, outcome, and emotion.}"
      service_used: "{Service Name}"
      verified_source: "Google"    # Google | Yelp | Facebook | Direct
      photo_url: "/images/testimonials/{slug}.jpg"
```

---

## Content Framework

**What makes a high-converting testimonial:**

```
SPECIFICITY  → Names a specific service, problem, or outcome
EMOTION      → Uses feeling words ("relieved", "impressed", "grateful")
DETAIL       → Mentions timeframe, price fairness, or staff name
RESULT       → States what changed after using the service
RELATABILITY → Written as the target customer would naturally speak
```

---

## Copy Example (3-Card Layout)

```markdown
## What Our Customers Say

⭐⭐⭐⭐⭐ Rated 4.9/5 from {N} Google Reviews

---

> "I had a burst pipe at midnight and {Brand} answered immediately. The technician arrived within 45 minutes and had everything fixed by 2am. Incredibly professional and the price was completely fair given the emergency. I won't use anyone else."
> — **Sarah M.**, Austin, TX · Emergency Plumbing · ✅ Verified Google Review

---

> "We've used {Brand} for all our commercial plumbing for three years. Their team is always on time, the work is clean, and they flag issues before they become expensive problems. Highly recommend for any business in the area."
> — **James T.**, Business Owner · Commercial Plumbing · ✅ Verified Google Review

---

> "Got three quotes for our water heater replacement. {Brand} wasn't the cheapest, but they were the most thorough in explaining what we needed and why. Installation was done in 2 hours, spotless cleanup. Very happy."
> — **Linda K.**, Round Rock, TX · Water Heater Install · ✅ Verified Google Review
```

---

## Schema Block (AggregateRating)

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "{brand_name}",
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "{rating_value}",
    "reviewCount": "{review_count}"
  },
  "review": [
    {
      "@type": "Review",
      "author": { "@type": "Person", "name": "{author_name}" },
      "datePublished": "{review_date}",
      "reviewRating": {
        "@type": "Rating",
        "ratingValue": "{rating}"
      },
      "reviewBody": "{review_text}"
    }
  ]
}
```

---

## Rules

- Only use real testimonials — fabricated reviews violate FTC guidelines and schema guidelines
- Mark testimonials with their source (Google, Yelp, etc.) for credibility
- Minimum 3 testimonials per page; 6 is ideal
- Include diverse reviewer profiles (homeowner, business, emergency, etc.)
- Photo of the reviewer significantly increases conversion rate

---

*Parent: [section-template.md](../_templates/section-template.md) | Used by: [page-template.md](../_templates/page-template.md)*
