---
description: Run a full technical SEO audit on a website with prioritized fix list
argument-hint: [url]
---

# Technical SEO Audit

1. Load client context from `.seo/`. If the URL doesn't match any client, offer to run `/new-client` first or run a standalone audit
2. Run the full audit workflow from the seo-technical-audit skill, executing these in parallel where possible:
   - URL discovery with `firecrawl map`
   - Robots.txt and sitemap validation
   - HTTP headers check on homepage + 5 key pages
   - Meta tags audit on 10-20 pages
   - Schema markup validation
   - Internal linking analysis
   - Core Web Vitals (if API key available)
   - Image optimization check
   - Mobile friendliness check
3. Compile results into a scored report (0-100 overall, per-category breakdown)
4. Save full audit to `.seo/clients/{slug}/technical/audit-{date}.json`
5. Display: overall score, category scores, top 10 priority fixes ranked by impact/effort ratio
