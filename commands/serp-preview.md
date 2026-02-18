---
description: Show how a page appears in Google search results with rich snippet eligibility
argument-hint: [url]
---

# SERP Preview

1. Scrape the target URL with firecrawl (both markdown and HTML formats)
2. Extract: title tag, meta description, canonical URL, all schema markup
3. Render a text-based SERP preview showing:
   - Title (truncated at 60 chars / ~580px with ellipsis if needed)
   - Display URL (domain > path breadcrumb format)
   - Meta description (truncated at 155 chars with ellipsis if needed)
4. Check rich result eligibility based on existing schema markup:
   - FAQ (FAQPage schema) — show expandable Q&A indicator
   - Review Stars (AggregateRating) — show star rating
   - Breadcrumbs (BreadcrumbList) — show breadcrumb path
   - Sitelinks (clear navigation structure) — show indicator
   - Video (VideoObject) — show video thumbnail indicator
   - Product (Product schema with price) — show price indicator
5. Flag issues: title too long/short, description missing, no schema markup, missing OG image
6. Generate 3 optimized title tag alternatives and 3 meta description alternatives
7. Display everything in a clean, visual format
