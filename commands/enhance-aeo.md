---
description: Deep AI search discovery — mine real questions people ask LLMs, test your keywords across AI engines, and find AEO gaps competitors miss
argument-hint: [client-name or domain] [topic or keywords...]
---

# Enhanced AEO Discovery

This command runs 5 deep-discovery modules to uncover what real people ask AI engines and how visible your brand is in AI-generated answers.

1. Load client context from `.seo/`. If domain doesn't match a client, run standalone
2. If no topic/keywords provided, use the client's top target keywords. If none exist, ask for 3-5 keywords or a main topic
3. Run all 5 discovery modules below in sequence, saving results after each

## Module 1: People Also Ask (PAA) Chain Mining

Mine Google's "People Also Ask" boxes to uncover the exact questions people type — these are the same questions they ask ChatGPT and Perplexity.

```bash
firecrawl search "{keyword}" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/paa-main-{keyword-slug}.json --json
firecrawl search "what is {keyword}" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/paa-whatis-{keyword-slug}.json --json
firecrawl search "how to {keyword}" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/paa-howto-{keyword-slug}.json --json
firecrawl search "why {keyword}" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/paa-why-{keyword-slug}.json --json
firecrawl search "{keyword} vs" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/paa-vs-{keyword-slug}.json --json
```

From the results, extract:
- All "People Also Ask" questions found
- Group by intent: informational, navigational, commercial, transactional
- Flag questions you already answer vs gaps
- Output a deduplicated question list ranked by estimated frequency

## Module 2: Google Autocomplete Mining

Scrape Google's autocomplete suggestions — these reflect real-time search behavior and map directly to what users ask AI chatbots.

```bash
firecrawl search "{keyword} a" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/auto-a-{keyword-slug}.json --json
firecrawl search "{keyword} how" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/auto-how-{keyword-slug}.json --json
firecrawl search "{keyword} best" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/auto-best-{keyword-slug}.json --json
firecrawl search "{keyword} for" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/auto-for-{keyword-slug}.json --json
firecrawl search "{keyword} can" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/auto-can-{keyword-slug}.json --json
firecrawl search "{keyword} should" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/auto-should-{keyword-slug}.json --json
firecrawl search "{keyword} is" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/auto-is-{keyword-slug}.json --json
```

From the results, extract:
- All suggested completions / related searches
- Cluster by question type (what/how/why/best/vs/can/should)
- Cross-reference with PAA results from Module 1 — overlapping questions are highest priority
- Flag commercial intent suggestions (these convert)

## Module 3: Reddit & Quora Question Mining

Real people ask real questions on Reddit and Quora — these are the EXACT questions they later ask AI chatbots. LLMs are trained on this data.

```bash
firecrawl search "site:reddit.com {keyword}" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/reddit-{keyword-slug}.json --json
firecrawl search "site:quora.com {keyword}" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/quora-{keyword-slug}.json --json
firecrawl search "reddit {keyword} recommendations" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/reddit-recs-{keyword-slug}.json --json
firecrawl search "reddit best {keyword}" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/reddit-best-{keyword-slug}.json --json
```

From the results, extract:
- Thread titles (= the questions people ask)
- Top-voted answers (= what AI engines learn from and cite)
- Brand mentions in discussions (yours and competitors)
- Common pain points and decision criteria people mention
- Subreddits where your topic is discussed (these are communities to monitor)

## Module 4: AnswerThePublic-Style Question Mapping

Build a full question tree around the topic using question word variations.

```bash
firecrawl search "who {keyword}" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/atp-who-{keyword-slug}.json --json
firecrawl search "what {keyword}" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/atp-what-{keyword-slug}.json --json
firecrawl search "when {keyword}" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/atp-when-{keyword-slug}.json --json
firecrawl search "where {keyword}" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/atp-where-{keyword-slug}.json --json
firecrawl search "which {keyword}" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/atp-which-{keyword-slug}.json --json
firecrawl search "{keyword} without" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/atp-without-{keyword-slug}.json --json
firecrawl search "{keyword} with" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/atp-with-{keyword-slug}.json --json
firecrawl search "{keyword} near me" --scrape --limit 5 -o .seo/clients/{slug}/aeo/.firecrawl/atp-nearme-{keyword-slug}.json --json
```

Build a visual question map:
```
                          who uses {keyword}?
                         /
         what is {keyword}? --- how does {keyword} work?
        /                                                  \
{KEYWORD} --- when to use {keyword}?     {keyword} vs {competitor}
        \                                                  /
         where to find {keyword}? --- which {keyword} is best?
                         \
                          why {keyword}?
```

Compile ALL questions from Modules 1-4 into a master question list:
- Deduplicate across all sources
- Rank by frequency (appeared in multiple modules = higher priority)
- Tag source: PAA, Autocomplete, Reddit, Quora, Question Map
- Tag intent: Informational, Commercial, Navigational, Transactional
- Tag status: Answered on your site / Not answered / Partially answered

## Module 5: Automated AI Visibility Testing

Take the client's top keywords and systematically test AI search visibility.

```bash
# Test each keyword for AI Overview presence and citation
firecrawl search "{keyword-1}" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/ai-test-kw1.json --json
firecrawl search "{keyword-2}" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/ai-test-kw2.json --json
firecrawl search "{keyword-3}" --scrape --limit 10 -o .seo/clients/{slug}/aeo/.firecrawl/ai-test-kw3.json --json
# ... repeat for all top keywords (up to 20)
```

For each keyword, analyze:

| Keyword | AI Overview? | You Cited? | Top Cited Sources | Your Rank | Gap |
|---------|-------------|------------|-------------------|-----------|-----|
| {kw1} | Yes/No | Yes/No | source1, source2 | #N or N/A | High/Med/Low |

Then scrape the top-cited competitor pages:
```bash
firecrawl scrape {top-cited-url-1} -o .seo/clients/{slug}/aeo/.firecrawl/competitor-1.json --json
firecrawl scrape {top-cited-url-2} -o .seo/clients/{slug}/aeo/.firecrawl/competitor-2.json --json
```

Reverse-engineer WHY they get cited:
- Content structure (headings, lists, tables)
- Schema markup present
- Word count and depth
- FAQ sections
- Data/statistics included
- Author credentials visible

## Final Output

Save complete results to `.seo/clients/{slug}/aeo/enhance-aeo-{date}.json`

Display a consolidated report:

### 1. Question Discovery Summary
- Total unique questions found: {count}
- From PAA: {count} | Autocomplete: {count} | Reddit: {count} | Quora: {count} | Question Map: {count}
- Questions you answer: {count} | Gaps: {count}
- Top 10 highest-priority questions to answer (ranked by frequency + intent)

### 2. AI Visibility Scorecard
- Keywords tested: {count}
- Keywords with AI Overview: {count}
- Keywords where you're cited: {count}
- Keywords where competitors cited instead: {count}
- Overall AI visibility: {percentage}

### 3. Competitor AI Advantage Analysis
- Who gets cited most: {competitor list with citation counts}
- What they do differently: {structural patterns}
- Quick wins: content format changes that could get you cited

### 4. Action Plan
Priority-ranked list of:
1. Top 10 questions to create content for (highest frequency, not yet answered)
2. Top 5 existing pages to restructure for AI citation
3. Schema markup additions needed
4. Content gaps where competitors dominate AI results
5. Reddit/Quora communities to participate in for brand visibility

Offer to:
- Generate FAQ content from discovered questions (ready to add to site)
- Create FAQPage schema from top questions
- Build a content calendar targeting question gaps
- Run /aeo-check on specific pages identified as high-opportunity
