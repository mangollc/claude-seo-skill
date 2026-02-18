---
description: Detect stale or declining content that needs refreshing with priority ranking
argument-hint: [client-name]
---

# Content Decay Detection

1. Load client context and URL list from `.seo/clients/{slug}/technical/sitemap-urls.txt`
2. Identify content pages (blog posts, guides, articles) from the URL list by filtering for common patterns (/blog/, /guide/, /article/, /resources/)
3. Scrape a sample of 15-20 content pages with firecrawl (run in parallel)
4. For each page, check decay signals:
   - Year mentions older than 2024 in the content
   - "Published" or "updated" dates older than 12 months
   - Word count under 500 (thin content risk)
   - References to deprecated tools, old product versions, or discontinued services
   - "Best of [year]" or "[year] Guide" with non-current year
5. For high-priority decayed content, compare against current top 5 competitors for the same topic
6. Rank by refresh priority: high (multiple decay signals + competitive pressure), medium (1-2 signals), low (minor freshness issues)
7. Save results to `.seo/clients/{slug}/content/content-decay.json`
8. Display: list of decayed pages sorted by priority, specific decay signals found, recommended refresh actions for each
