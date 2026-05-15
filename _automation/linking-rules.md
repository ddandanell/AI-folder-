# Linking Rules

Automated internal linking rules that run after page generation. When `auto_internal_linking: true`, these rules are applied to every generated page.

---

## Rule Format

Each rule follows the structure:

```yaml
rule_id: "R-001"
trigger: "condition that activates the rule"
action: "what the rule does"
scope: "which pages this applies to"
max_per_page: N        # Max times this rule fires on a single page
priority: 1            # Lower number = applied first
```

---

## Rule Set: Service Mention Links

```yaml
- rule_id: "R-001"
  trigger: "First occurrence of {service.name} in body text"
  action: "Wrap in link to /{service.slug}/"
  anchor_text_type: "exact-match"
  scope: "all pages except /{service.slug}/ itself"
  max_per_page: 1
  priority: 1

- rule_id: "R-002"
  trigger: "Second occurrence of {service.name} in body text"
  action: "Wrap in link to /{service.slug}/ with partial-match anchor"
  anchor_text_examples:
    - "our {service.name} team"
    - "professional {service.name}"
    - "{service.name} services"
  scope: "all pages except /{service.slug}/ itself"
  max_per_page: 1
  priority: 2
```

---

## Rule Set: City Name Links

```yaml
- rule_id: "R-010"
  trigger: "First occurrence of {city.name} in body text"
  action: "Wrap in link to /{primary_service}/{city.slug}/"
  anchor_text_type: "partial-match"
  scope: "non-city pages only"
  max_per_page: 1
  priority: 3

- rule_id: "R-011"
  trigger: "City page mentions a nearby city (within radius)"
  action: "Add 'Also serving {nearby_city.name}' link in contact section"
  anchor_text: "{primary_service} in {nearby_city.name}"
  link_destination: "/{primary_service}/{nearby_city.slug}/"
  scope: "city pages only"
  max_per_page: 3
  priority: 4
```

---

## Rule Set: Blog-to-Pillar Links

```yaml
- rule_id: "R-020"
  trigger: "Blog post mentions {service.name}"
  action: "Inject contextual CTA block after the paragraph"
  cta_template: |
    > **Need professional {service.name}?** [{brand_name}]({domain}/{service.slug}/) offers
    > [fast, reliable {service.name}](/{service.slug}/) in {primary_city}. [Get a free quote](#contact).
  scope: "blog posts only"
  max_per_page: 2
  priority: 5

- rule_id: "R-021"
  trigger: "Blog post is published"
  action: "Add to 'Related Posts' section on the most relevant pillar page"
  scope: "pillar pages"
  max_per_pillar: 10
  priority: 6
```

---

## Rule Set: FAQ Answer Links

```yaml
- rule_id: "R-030"
  trigger: "FAQ answer mentions a city the business serves"
  action: "Link city name to /{primary_service}/{city.slug}/"
  scope: "faq sections"
  max_per_page: 5
  priority: 7

- rule_id: "R-031"
  trigger: "FAQ answer describes a specific service"
  action: "Link service name to /{service.slug}/"
  scope: "faq sections"
  max_per_page: 5
  priority: 8
```

---

## Rule Set: Footer / Navigation Auto-Links

```yaml
- rule_id: "R-040"
  trigger: "New pillar page created"
  action: "Add to main navigation menu"
  navigation_slot: "primary"
  priority: 1

- rule_id: "R-041"
  trigger: "New city page created"
  action: "Add to footer service area section"
  footer_slot: "service-areas"
  max_in_footer: 20
  priority: 2

- rule_id: "R-042"
  trigger: "New blog post created"
  action: "Add to footer blog section (latest 5)"
  footer_slot: "recent-posts"
  max_in_footer: 5
  rolling: true        # Always shows latest N, drops oldest
  priority: 3
```

---

## Rule Set: Anchor Text Variation

To ensure anchor text diversity across the site:

```yaml
- rule_id: "R-050"
  trigger: "Any page links to /{service.slug}/ more than once"
  action: "Vary anchor text: exact → partial → generic rotation"
  rotation_pool:
    exact: "{primary_keyword}"
    partial:
      - "our {service.name} services"
      - "professional {service.name} in {primary_city}"
      - "{service.name} specialists"
    generic:
      - "learn more"
      - "find out more"
      - "our team"
      - "get a quote"
  priority: 9
```

---

## Conflict Resolution

When two rules would place a link on the same text occurrence:

1. **Higher priority rule wins** (lower rule_id number = higher priority)
2. If same priority: **more specific scope wins** (city page rule > all-pages rule)
3. If still tied: apply only the first match; log the conflict

---

## Linking Rules Audit

Run weekly:

```
[ ] No link points to a 404 page
[ ] No link points to a redirect chain (should go directly to final destination)
[ ] Anchor text ratios are within spec (see internal-linking.md)
[ ] No page has more than 20 outbound internal links
[ ] No valuable page is orphaned (0 inbound internal links)
[ ] Footer navigation matches current site structure
[ ] Blog-to-pillar links are present on all published posts
```

---

*Parent: [page-generator.md](./page-generator.md) | See also: [_seo/internal-linking.md](../_seo/internal-linking.md)*
