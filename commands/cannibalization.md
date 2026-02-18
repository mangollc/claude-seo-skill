---
description: Find pages on the same site competing for the same keywords with fix recommendations
argument-hint: [client-name]
---

# Cannibalization Detection

1. Load client context and URL list from `.seo/clients/{slug}/technical/sitemap-urls.txt`
2. If no URL list exists, run `firecrawl map {domain}` first
3. Scrape title tags and H1s from all key pages (service pages, blog posts, landing pages)
4. Group pages by similar title keywords — pages sharing the same primary keyword target are candidates
5. For each candidate group, search Google via firecrawl to check if multiple client pages appear in top 20 results for the same query
6. For each confirmed cannibalization case, recommend one of:
   - **Merge**: both pages are thin — combine into one comprehensive page, 301 redirect the other
   - **Differentiate**: pages serve different intents — adjust titles/content to target distinct keywords
   - **Canonical**: one page is clearly stronger — canonical the weaker to the stronger
7. Save results to `.seo/clients/{slug}/content/cannibalization.json`
8. Display: list of cannibalized keyword groups, affected URLs, recommended action for each
