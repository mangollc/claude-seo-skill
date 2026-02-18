---
description: Check a brand's visibility in AI search engines (Google AI Overview, Perplexity, ChatGPT)
argument-hint: [brand-name or domain] [target-queries...]
---

# AEO Check

1. Load client context from `.seo/`. If brand/domain doesn't match a client, run as a standalone check
2. If no target queries provided, use the client's top 5 target keywords from keyword research. If none exist, ask the user for 3-5 queries to check
3. For each target query, search via firecrawl and analyze:
   - Does a Google AI Overview appear for this query?
   - Which sources are cited in AI-related features?
   - Is the client/brand cited or mentioned?
   - Which competitors appear in AI results?
4. Run a brand authority signals check: Wikipedia, Wikidata, Knowledge Panel, social profiles, news coverage, Organization schema
5. Score the brand's overall AEO readiness (per-page checklist from seo-aeo skill)
6. Save results to `.seo/clients/{slug}/aeo/ai-overview-audit-{date}.json`
7. Display: visibility summary per query (cited/not cited), competitor AI presence, brand authority score, top 5 recommendations to improve AI search visibility
