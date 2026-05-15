# Schema Templates

Complete JSON-LD schema templates for all page types. Inject into `<head>` via a `<script type="application/ld+json">` tag. Variables in `{curly_braces}` are replaced at render time from `project-config.md`.

---

## 1. Organization (Homepage)

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "{brand_name}",
  "url": "{domain}",
  "logo": {
    "@type": "ImageObject",
    "url": "{domain}/images/logo-light.svg",
    "width": 200,
    "height": 60
  },
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "{phone}",
    "contactType": "customer service",
    "availableLanguage": "English"
  },
  "sameAs": [
    "{social.facebook}",
    "{social.instagram}",
    "{social.linkedin}",
    "{social.twitter}"
  ]
}
```

---

## 2. LocalBusiness (Service Business / City Pages)

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "{brand_name}",
  "description": "{tagline}",
  "url": "{canonical}",
  "telephone": "{phone}",
  "email": "{email}",
  "image": "{domain}{og_image}",
  "priceRange": "$$",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "{address.street}",
    "addressLocality": "{address.city}",
    "addressRegion": "{address.state}",
    "postalCode": "{address.zip}",
    "addressCountry": "{address.country}"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "{lat}",
    "longitude": "{lng}"
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
  ],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "{aggregate_rating.rating_value}",
    "reviewCount": "{aggregate_rating.review_count}"
  }
}
```

---

## 3. Service (Service Pages)

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "name": "{service.name}",
  "description": "{service.short_description}",
  "provider": {
    "@type": "LocalBusiness",
    "name": "{brand_name}",
    "url": "{domain}"
  },
  "areaServed": {
    "@type": "City",
    "name": "{address.city}"
  },
  "serviceType": "{service.name}",
  "url": "{canonical}"
}
```

---

## 4. FAQPage (FAQ Sections / Pages)

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "{faq.question}",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "{faq.answer}"
      }
    }
  ]
}
```

*Note: Repeat the `Question` block for each FAQ item. Maximum 10 per page for optimal rich result eligibility.*

---

## 5. Article (Blog Posts)

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "{title}",
  "description": "{description}",
  "image": "{domain}{og_image}",
  "author": {
    "@type": "Person",
    "name": "{author_name}",
    "url": "{domain}/about/"
  },
  "publisher": {
    "@type": "Organization",
    "name": "{brand_name}",
    "logo": {
      "@type": "ImageObject",
      "url": "{domain}/images/logo-light.svg"
    }
  },
  "datePublished": "{date_created}",
  "dateModified": "{date_modified}",
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "{canonical}"
  }
}
```

---

## 6. BreadcrumbList (All pages except Homepage)

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "{domain}"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "{parent_page_name}",
      "item": "{domain}{parent_page_slug}"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "{current_page_name}",
      "item": "{canonical}"
    }
  ]
}
```

---

## 7. WebSite (Homepage — enables Sitelinks Search Box)

```json
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "name": "{brand_name}",
  "url": "{domain}",
  "potentialAction": {
    "@type": "SearchAction",
    "target": {
      "@type": "EntryPoint",
      "urlTemplate": "{domain}/search?q={search_term_string}"
    },
    "query-input": "required name=search_term_string"
  }
}
```

---

## 8. Review (Individual Testimonials)

```json
{
  "@context": "https://schema.org",
  "@type": "Review",
  "itemReviewed": {
    "@type": "LocalBusiness",
    "name": "{brand_name}"
  },
  "reviewRating": {
    "@type": "Rating",
    "ratingValue": "{rating}",
    "bestRating": "5"
  },
  "author": {
    "@type": "Person",
    "name": "{author_name}"
  },
  "datePublished": "{review_date}",
  "reviewBody": "{review_text}"
}
```

---

## Schema Injection Rules

1. **Never inject schema not validated** — always test in [Google's Rich Results Test](https://search.google.com/test/rich-results)
2. **Multiple schemas on one page**: wrap in a JSON array `[{...}, {...}]` or use multiple `<script>` tags
3. **BreadcrumbList**: inject on all pages except the homepage
4. **FAQPage**: inject only when ≥ 5 real Q&A pairs exist
5. **AggregateRating**: only inject when real review data is available — never fabricate

---

*Parent: [seo-framework.md](./seo-framework.md) | See also: [metadata-template.md](../_templates/metadata-template.md)*
