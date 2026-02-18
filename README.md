# Claude SEO Skill

A comprehensive SEO and AEO (AI Engine Optimization) plugin for [Claude Code](https://docs.anthropic.com/en/docs/claude-code). Built for agencies managing multiple clients. Covers keyword strategy, technical audits, content optimization, local SEO, backlinks, and AI search optimization.

## Features

- **6 Skills** with deep, actionable workflows
- **13 Slash Commands** for quick actions
- **Multi-Client Support** with organized data per client
- **Revenue-Focused** keyword research (not vanity metrics)
- **AI Search Ready** optimization for Google AI Overviews, Perplexity, and ChatGPT
- **Agency Reporting** with reusable monthly report templates

## Installation

### Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed
- [Firecrawl CLI](https://firecrawl.dev) for web scraping:

```bash
npm install -g firecrawl-cli
firecrawl login --browser
```

### Install the Plugin

**Option 1: Install from GitHub (recommended)**

```bash
claude plugin add mangollc/claude-seo-skill
```

**Option 2: Clone and use directly**

```bash
git clone https://github.com/mangollc/claude-seo-skill.git
cd claude-seo-skill
claude
```

**Option 3: Add to an existing project**

```bash
cd /path/to/your-project
claude plugin add mangollc/claude-seo-skill
```

## Quick Start

```
1. /new-client "My Business"          Set up client profile + initial site crawl
2. /audit https://mybusiness.com      Full technical SEO audit (scored 0-100)
3. /keywords "target topic" --local   Keyword research with clustering
4. /score-page https://url "keyword"  On-page SEO score with fix list
5. /report "my-business"              Monthly SEO report
```

## Commands

| Command | Arguments | Description |
|---------|-----------|-------------|
| `/new-client` | `{name}` | Create a new client profile with directory structure and initial site crawl |
| `/audit` | `{url}` | Full technical SEO audit: crawlability, meta tags, schema, internal links, CWV, speed, mobile |
| `/keywords` | `{topic} [--local\|--saas]` | Revenue-focused keyword research with clustering, intent mapping, and difficulty scoring |
| `/topic-map` | `{client} {topic}` | Build a topical authority map with pillar pages and cluster content architecture |
| `/score-page` | `{url} {keyword}` | Score a page's on-page SEO (0-100) across 10 categories with actionable fixes |
| `/serp-preview` | `{url}` | Preview how a page appears in Google search results + rich snippet eligibility check |
| `/cannibalization` | `{client}` | Find pages competing for the same keywords with merge/differentiate/canonical recommendations |
| `/content-decay` | `{client}` | Detect stale or declining content with prioritized refresh recommendations |
| `/gbp-calendar` | `{client}` | Generate a 30-day Google Business Profile posting calendar with ready-to-publish posts |
| `/schema` | `{url} [type]` | Generate valid JSON-LD structured data (auto-detects page type if not specified) |
| `/aeo-check` | `{brand} {queries...}` | Check brand visibility in AI search engines (Google AI Overview, Perplexity, ChatGPT) |
| `/brand-serp` | `{brand}` | Analyze and optimize what appears when someone searches your brand name |
| `/report` | `{client} [month]` | Generate a monthly SEO report from all collected data with trends and action items |

## Skills

### 1. Keyword Strategy (`seo-keywords`)

Two distinct workflows depending on business model:

**Local/Service Businesses:**
- Geo-modified keyword discovery (service + city combinations)
- Competitor keyword extraction from local SERPs
- Revenue-mapped keyword prioritization
- "Near me" and hyperlocal variants

**SaaS/Online Companies:**
- Product-led keyword discovery
- BOFU/MOFU/TOFU funnel classification
- Feature vs problem keyword mapping
- Comparison and alternative keywords

**Both workflows include:**
- Keyword clustering by SERP overlap
- Search intent classification (transactional, commercial, informational, navigational)
- Difficulty scoring (1-10) via SERP analysis
- Topical authority mapping (pillar + cluster architecture)
- SERP feature analysis (Featured Snippets, PAA, AI Overview, etc.)
- Competitor content strategy reverse engineering
- Programmatic SEO templates (location pages, comparison pages, category pages)

### 2. Technical SEO Audit (`seo-technical-audit`)

Full site health assessment scored 0-100:

- **Crawlability**: URL discovery, orphan pages, status codes, redirect chains
- **Robots.txt & Sitemap**: validation, cross-referencing
- **HTTP Headers**: canonical, X-Robots-Tag, security, caching
- **Meta Tags**: title, description, canonical, Open Graph, Twitter Cards, hreflang, robots directives
- **Schema/JSON-LD**: validation + generation (LocalBusiness, Article, Product, FAQ, HowTo, Organization, BreadcrumbList, WebSite)
- **Internal Linking**: link graph, orphan pages, link depth, anchor text distribution
- **Core Web Vitals**: LCP, CLS, INP via PageSpeed Insights API
- **Page Speed Playbook**: render-blocking resources, image compression, critical CSS, font loading, third-party scripts
- **Image Optimization**: alt text, format (WebP), lazy loading, responsive images, dimensions
- **Mobile Friendliness**: viewport, responsive, tap targets, font sizes
- **SERP Feature Eligibility**: FAQ, How-to, Review Stars, Breadcrumbs, Sitelinks, Video, Product
- **Crawl Budget Analysis**: thin content, duplicate content, faceted navigation, parameter handling
- **International SEO**: hreflang audit, language targeting, URL structure recommendations
- **Cannibalization Detection**: pages competing for same keywords with fix recommendations

### 3. Content Optimization (`seo-content`)

**On-Page Scoring (0-100 rubric):**

| Category | Points | What's Checked |
|----------|--------|----------------|
| Title Tag | 15 | Length, keyword position, uniqueness, SERP truncation |
| Meta Description | 10 | Length, CTA, keyword, uniqueness |
| H1 Tag | 10 | Single H1, contains keyword |
| Heading Hierarchy | 10 | Proper nesting, keywords in subheadings |
| Content Depth | 15 | Word count vs competitors, topic coverage |
| Keyword Usage | 10 | Density, first 100 words, LSI/semantic terms |
| Internal Links | 10 | Min 3, relevant anchors, pillar links |
| Image Optimization | 10 | Alt text, format, lazy loading, dimensions |
| URL Structure | 5 | Length, keyword, no parameters |
| Social Meta | 5 | OG tags, Twitter Cards |

**Also includes:**
- SERP preview generator (title truncation, description preview, rich snippet check)
- Content readability analysis (Flesch-Kincaid grade level)
- E-E-A-T analysis (Experience, Expertise, Authoritativeness, Trustworthiness)
- Featured snippet optimization (paragraph, list, table formats)
- Content gap analysis vs competitors
- Content decay detection (outdated stats, stale references, thin content)
- Pre-publish checklist (comprehensive markdown template)
- Title/meta description generator (3-5 optimized options)

### 4. Local SEO (`seo-local`)

- **GBP Post Generation**: 5 post types (What's New, Offer, Event, Product Highlight, Educational)
- **30-Day Posting Calendar**: 12-16 posts/month, rotating services and areas, seasonal relevance
- **NAP Consistency Audit**: check Name, Address, Phone across major directories
- **Local Citation Audit**: 50+ citation sources organized by industry (home services, restaurants, healthcare, legal, real estate, automotive)
- **Review Response Templates**: 5 positive + 5 negative response templates with personalization
- **Local Keyword Optimization**: geo-modified variants mapped to landing pages

### 5. Backlinks & Reporting (`seo-backlinks`)

- **Competitor Backlink Profiling**: discover link sources via brand mentions, guest posts, directories
- **Link Opportunity Scoring**: 0-100 score across relevance, authority, achievability, traffic potential
- **90-Day Outreach Plan**:
  - Phase 1 (Days 1-30): directories, unlinked mentions, broken links
  - Phase 2 (Days 31-60): guest posts, resource pages, HARO, podcasts
  - Phase 3 (Days 61-90): digital PR, data-driven content, partnerships
- **Outreach Email Templates**: guest post pitch, unlinked mention, broken link outreach
- **Toxic Backlink Identification**: PBN detection, spam patterns, disavow file generation
- **Unlinked Mention Discovery**: find brand mentions without links
- **Monthly Reporting Framework**: reusable template with executive summary, metrics, trends, action items

### 6. AI Search Optimization (`seo-aeo`)

- **Google AI Overview Optimization**: analyze cited sources, content formatting for citation
- **Perplexity Citation Optimization**: factual accuracy, structured content, source credibility
- **ChatGPT/Bing Optimization**: entity signals, Wikipedia/Wikidata presence, Bing SEO
- **AI-Focused Structured Data**: FAQPage, HowTo, DefinedTerm, speakable, Organization with sameAs
- **FAQ & Entity Optimization**: People Also Ask mining, entity-first writing
- **Brand Authority Signals Audit**: Knowledge Panel, Wikipedia, social profiles, news coverage
- **Brand SERP Management**: analyze page 1 of brand search, owned vs unowned results, sentiment
- **Per-Page AEO Checklist**: 100-point scoring across 11 AI-readiness factors

## Multi-Client Data Structure

All working data is stored in `.seo/` (gitignored):

```
.seo/
├── config.json                    # Agency-level defaults
└── clients/{client-slug}/
    ├── config.json                # Client profile (domain, competitors, business type)
    ├── keywords/                  # Research, clusters, topic maps
    ├── technical/                 # Audit results, schema markup, CWV data
    │   └── schema-markup/         # Generated JSON-LD files
    ├── content/                   # Page scores, content gaps, decay reports
    ├── local/                     # GBP posts, calendars, NAP audit
    │   └── gbp-posts/
    ├── backlinks/                 # Competitor profiles, outreach plans
    ├── aeo/                       # AI search audits, entity data
    └── reports/                   # Monthly and quarterly reports
```

## Supported Business Types

- **Local/Service Businesses** (plumbers, lawyers, dentists, restaurants, etc.)
- **SaaS Companies** (software products, online tools)
- **E-commerce** (online stores, product catalogs)
- **Publishers** (blogs, news sites, content sites)

## How It Works

This plugin provides Claude Code with detailed SEO workflows and instructions. When you invoke a command or skill, Claude:

1. Loads your client configuration from `.seo/clients/{slug}/config.json`
2. Uses **Firecrawl CLI** to scrape, crawl, and search the web
3. Analyzes the data following the skill's methodology
4. Saves structured results (JSON) and readable reports (Markdown) to `.seo/`
5. Presents findings with scores, prioritized recommendations, and next steps

## License

MIT

## Contributing

Contributions welcome. Please open an issue or pull request on [GitHub](https://github.com/mangollc/claude-seo-skill).
