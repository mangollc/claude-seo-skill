---
description: Run keyword research for a topic or URL with clustering and intent mapping
argument-hint: [topic or url] [--local|--saas]
---

# Keyword Research

1. Load client context from `.seo/`. If no client exists, prompt to run `/new-client` first
2. Determine business type from the `--local` or `--saas` flag, or from client config `business_type`
3. Run the appropriate keyword workflow from the seo-keywords skill:
   - Local: seed keywords from service + location combos, competitor extraction, geo-modified expansion
   - SaaS: product-led discovery, funnel-stage classification, feature vs problem keywords
4. Cluster keywords by SERP overlap (keywords sharing 3+ top 10 results = same cluster)
5. Classify search intent for each keyword (transactional, commercial, informational, navigational)
6. Assess difficulty (1-10) based on top 10 SERP analysis
7. Map revenue potential (high/medium/low)
8. Save full results to `.seo/clients/{slug}/keywords/research-{date}.json`
9. Save clusters to `.seo/clients/{slug}/keywords/clusters.json`
10. Display summary: total keywords found, clusters identified, top 10 priority keywords with intent and difficulty
