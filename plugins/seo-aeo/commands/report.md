---
description: Generate a monthly SEO report for a client from all collected data
argument-hint: [client-name] [month]
---

# Monthly Report

1. Load client context from `.seo/clients/{slug}/config.json`
2. If month not specified, use the current month
3. Gather data from all subdirectories:
   - `technical/` — latest audit scores, issues fixed
   - `keywords/` — keyword tracking, new opportunities
   - `content/` — pages published, scores, content gaps
   - `local/` — GBP posts published, review count
   - `backlinks/` — links acquired/lost, outreach stats
   - `aeo/` — AI search visibility
4. Compare against previous month's report if it exists in `reports/`
5. Calculate trends (improving, declining, stable) for each metric
6. Generate the full report following the monthly report template from the seo-backlinks skill
7. Save to `.seo/clients/{slug}/reports/monthly-{year}-{month}.md`
8. Display the executive summary and key metrics. Offer to show the full report
