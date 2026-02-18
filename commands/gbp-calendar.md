---
description: Generate a 30-day Google Business Profile posting calendar with ready-to-publish posts
argument-hint: [client-name]
---

# GBP Calendar

1. Load client context from `.seo/clients/{slug}/config.json`. Require `gbp` section with business name, services, service areas
2. Research competitors: search `"{service} {city}"` via firecrawl to analyze what local competitors post
3. Determine current month and any upcoming holidays, seasonal events, or local events
4. Generate 12-16 posts (3-4 per week) following the seo-local skill calendar rules:
   - Rotate post types: What's New, Offer, Event, Product/Service Highlight, Educational/Tips
   - Rotate services from the client's services list
   - Rotate service areas
   - Include local keywords naturally
   - Each post: title, body (150-250 words), CTA text + URL, photo suggestion, target keyword
5. Save calendar to `.seo/clients/{slug}/local/gbp-posts/calendar-{month}-{year}.json`
6. Save individual posts to `.seo/clients/{slug}/local/gbp-posts/posts/post-{date}-{slug}.md`
7. Display: calendar overview with dates, post types, and titles. Ask if user wants to see full content of any specific post
