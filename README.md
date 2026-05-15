# AI-folder-

## SEO setup add-on: dataflow først

SEO-systemet skal bygges som et dataflow, ikke som “vi laver sider og håber”.

### 1. Definer målet

Målet er hele kæden:

`Keyword → Page → City → Service → Visitor → CTA click → Form/WhatsApp/call → Qualified lead → Sale value`

Det betyder, at SEO måles på forretningsværdi, ikke kun trafik.

### 2. Fast datamodel pr. side

Hver side skal have faste datafelter:

- `page_type`
- `service`
- `city`
- `keyword_target`
- `template_version`
- `cta_type`
- `content_batch`

Eksempel:

```txt
page_type: service_page
service: private_chef
city: canggu
keyword_target: private chef canggu
template_version: service_city_v1
cta_type: whatsapp
content_batch: 2026_05_batch_01
```

Det gør det muligt at måle, hvilken service, by, template, CTA og content batch der performer bedst.

### 3. Tracking-stack i lag

#### GTM
GTM er kontrolboksen. Events som minimum:

- `page_view`
- `scroll_50`
- `scroll_90`
- `cta_click`
- `whatsapp_click`
- `phone_click`
- `form_start`
- `form_submit`
- `booking_submit`
- `pricing_view`
- `faq_open`
- `internal_link_click`
- `service_card_click`
- `city_card_click`
- `menu_download`
- `lead_qualified`
- `sale_closed`

#### GA4
GA4 måler brugeradfærd efter klik. Vigtige events:

- `page_view`
- `session_start`
- `first_visit`
- `generate_lead`
- `form_submit`
- `click_to_whatsapp`
- `click_to_call`
- `booking_request`
- `quote_request`
- `view_service`
- `view_city`
- `view_pricing`

Vigtige dimensions:

- `landing_page`
- `page_path`
- `source`
- `medium`
- `campaign`
- `device_category`
- `country`
- `city`
- `event_name`
- `conversion`
- `session_default_channel_group`

#### Search Console
Search Console måler performance før klik:

- `queries`
- `impressions`
- `clicks`
- `CTR`
- `average position`
- `page`
- `country`
- `device`
- `date`

#### Google Ads data
Bruges til:

- keyword validation
- CPC-estimat
- commercial intent
- conversion-rate test
- landing page test
- search term discovery

#### CRM / lead database
Hvert lead skal gemmes med:

- `lead_id`
- `date`
- `source`
- `landing_page`
- `service`
- `city`
- `keyword_group`
- `form_answers`
- `lead_quality`
- `estimated_value`
- `status`
- `closed_won / closed_lost`
- `revenue`
- `reason_lost`

Det vigtigste output er: **revenue per landing page**.

#### Rank tracking
Kun støtte-data:

- `keyword`
- `target_page`
- `position`
- `SERP features`
- `competitors`
- `city/local variation`
- `movement over time`

#### Crawl / audit data

- `status code`
- `indexable / noindex`
- `canonical`
- `title length`
- `missing meta`
- `H1 count`
- `word count`
- `internal links in`
- `internal links out`
- `orphan pages`
- `schema status`
- `page speed`
- `image size`
- `broken links`

### 4. Saml alt på én nøgle

Alle datakilder skal samles på `page_id` eller URL.

Eksempel:

`/bali/private-chef/canggu`

Den side skal kunne forbindes til:

- GSC: impressions, clicks, CTR, position
- GA4: sessions, engagement, CTA clicks, conversions
- CRM: leads, qualified leads, sales, revenue
- Crawl: technical health, internal links, indexability
- Rank tracking: keyword positions

### 5. Validering af tracking

Test manuelt:

- WhatsApp
- Phone
- Form
- CTA
- Menu
- FAQ
- Internal links

Tjek i:

- GTM Preview
- GA4 DebugView
- GA4 Realtime
- Database logs
- CRM lead entry

Sammenlign altid tracking-data med databasen. Hvis GA4 og CRM ikke matcher, er der fejl eller spam-filtrering.

Brug også konsistente UTM-parametre:

```txt
utm_source=google
utm_medium=organic
utm_campaign=seo
utm_content=private_chef_canggu
```

Rigtig rækkefølge ved formular:

`User submits form → server saves lead → lead_id created → GA4 event sent → CRM updated → notification sent → dashboard updated`

### 6. Prioritering

#### Første 30 dage

- Fix tracking
- Fix indexing
- Fix titles
- Fix internal links
- Fix main service pages
- Fix Google Business Profile
- Fix conversion tracking

#### Dag 30-90

- Byg service-city pages
- Byg keyword pages
- Byg FAQ clusters
- Byg supporting articles
- Mål impressions, CTR, position, indexed pages, CTA clicks og lead rate

#### Dag 90-180

Optimer efter data:

- høj impression + lav CTR → fix title/meta
- høj trafik + ingen leads → fix offer, CTA, trust, form
- ikke indexeret → fix content, internal links, canonical, sitemap
- position 8-20 → tilføj depth, links, backlinks
- sider med leads → byg flere versioner omkring samme vinder

### 7. KPI-rækkefølge

1. Indexed pages
2. Impressions
3. Clicks
4. CTR
5. Average position
6. Engaged sessions
7. CTA clicks
8. Form/WhatsApp/call leads
9. Qualified leads
10. Closed sales
11. Revenue per page
12. Revenue per service
13. Revenue per city
14. Revenue per content cluster

### 8. Page Performance Dashboard

Dashboardet skal være et page performance dashboard, ikke kun et SEO-dashboard.

Kolonner:

- URL
- Page type
- Service
- City
- Target keyword
- Impressions
- Clicks
- CTR
- Position
- Sessions
- CTA clicks
- Leads
- Qualified leads
- Sales
- Revenue
- Internal links
- Index status
- Last updated
- Next action

Det skal gøre det muligt at vælge:

- Keep
- Improve
- Expand
- Merge
- Delete
- Add links
- Rewrite title
- Rewrite content
- Build backlinks
- Create more similar pages

### 9. Hurtige vs. langsomme SEO-effekter

#### Hurtige signaler

- title tags
- meta descriptions
- internal linking
- crawl/index fixes
- page speed
- content refreshes
- FAQ/schema
- Google Business Profile

#### Mellem-hastighed

- nye service pages
- city pages
- topical clusters
- link building
- behavioral signals

#### Langsomme, stærke assets

- brand
- domain authority
- semantic authority
- content ecosystem
- link profile
- historical trust
- AI search authority

### 10. SEO-lagene i korrekt rækkefølge

1. Strategisk fundament
2. Teknisk fundament
3. Side-arkitektur
4. Template-system
5. Content-produktion
6. Intern linking engine
7. Semantisk dækning
8. Trust og conversion
9. Tracking og data
10. Crawling, audit og forbedring
11. Skalering
12. Autoritet
13. AI Search Optimization
14. Profit-optimering

Den rigtige regel er:

- strategi før teknik
- arkitektur før content
- templates før skalering
- tracking før store beslutninger
- data før optimering
- autoritet efter fundamentet

### 11. Kerneprincip

- SEO uden data = gætteri
- SEO med GSC = synlighed
- SEO med GA4 = brugeradfærd
- SEO med CRM = forretning
- SEO med revenue tracking = maskine
