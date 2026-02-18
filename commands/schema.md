---
description: Generate valid JSON-LD structured data for a page
argument-hint: [url] [schema-type]
---

# Generate JSON-LD Schema

1. Scrape the target URL with `firecrawl scrape {url} --format markdown,links`
2. If schema type is provided, generate that specific type. If not, auto-detect the best type based on page content:
   - Homepage → Organization + WebSite (with SearchAction)
   - Service page → LocalBusiness or Service
   - Product page → Product (with AggregateRating if reviews present)
   - Blog post → Article (with author, dates, publisher)
   - FAQ page → FAQPage (extract Q&A pairs from content)
   - How-to / tutorial → HowTo (extract steps)
   - About page → Organization (with sameAs social links)
   - Contact page → LocalBusiness (with address, phone)
3. Also generate BreadcrumbList schema for any page with clear navigation hierarchy
4. Validate: all required properties present, proper @context, valid types
5. Save to `.seo/clients/{slug}/technical/schema-markup/{page-slug}.jsonld`
6. Display the generated JSON-LD and instructions for adding it to the page (paste in `<head>` inside `<script type="application/ld+json">`)
