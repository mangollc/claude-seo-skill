---
description: Analyze and optimize what appears when someone searches your brand name
argument-hint: [brand-name]
---

# Brand SERP Analysis

1. Load client context from `.seo/`. If brand name provided doesn't match a client, run as standalone
2. Search the brand name via firecrawl with scraping enabled to capture full first page of results
3. For each result on page 1, identify:
   - URL, domain, page type (homepage, social, review site, news, directory)
   - Sentiment (positive, neutral, negative)
   - Whether the client owns/controls this result
4. Check for Knowledge Panel presence and accuracy
5. Map which positions are owned (homepage, social profiles, blog) vs unowned (reviews, press, directories)
6. Identify negative or concerning results that need attention
7. Check competitor brand SERPs for comparison (search competitor brand names)
8. Save analysis to `.seo/clients/{slug}/aeo/brand-serp-{date}.json`
9. Display: visual map of brand SERP (positions 1-10 with type and sentiment), owned vs unowned breakdown, priority actions to improve brand SERP (e.g., claim missing social profiles, generate press coverage, respond to negative reviews)
