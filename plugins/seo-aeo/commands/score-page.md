---
description: Score a page's on-page SEO (0-100) with actionable fixes
argument-hint: [url] [target-keyword]
---

# Score Page

1. Scrape the target URL with firecrawl (both markdown+links and HTML formats)
2. If no target keyword provided, infer from the page title and H1
3. Run the full on-page scoring rubric from the seo-content skill across all 10 categories:
   - Title tag (15 pts), Meta description (10 pts), H1 (10 pts), Heading hierarchy (10 pts)
   - Content depth (15 pts), Keyword usage (10 pts), Internal links (10 pts)
   - Image optimization (10 pts), URL structure (5 pts), Social meta (5 pts)
4. Compare content depth against top 5 competitors for the target keyword
5. Run readability analysis (Flesch-Kincaid grade level)
6. Run E-E-A-T quick assessment
7. Save detailed score to `.seo/clients/{slug}/content/page-scores/{url-slug}-score.json`
8. Display: total score (0-100), category breakdown, top 5 most impactful fixes, readability grade
