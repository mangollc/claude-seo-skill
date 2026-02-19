# SEO AEO Pro

> **Last updated: February 19, 2026**

Your AI-powered SEO assistant. Just type simple commands and get professional-grade SEO analysis, keyword research, content scoring, and more — no SEO expertise required.

Works with any website. Built for agencies managing multiple clients.

---

## What Can It Do?

**Think of it as having an SEO expert on your team that works instantly.**

- **Check your website's health** — find and fix technical problems hurting your Google rankings
- **Find the right keywords** — discover what your customers are actually searching for
- **Score any page** — get a 0-100 SEO score with a clear list of what to fix
- **See how Google shows your page** — preview your search result before publishing
- **Create social posts** — generate a full month of Google Business Profile posts
- **Build link strategies** — find where competitors get their backlinks and create outreach plans
- **Get found in AI search** — optimize for Google AI Overviews, Perplexity, and ChatGPT
- **Monthly reports** — auto-generate professional SEO reports for clients

---

## Getting Started

### What You Need

1. **Claude Code** — the AI coding assistant from Anthropic
   - Install it: https://docs.anthropic.com/en/docs/claude-code

2. **Firecrawl** — used behind the scenes to read websites
   - Open your terminal and run:
   ```
   npm install -g firecrawl-cli
   firecrawl login --browser
   ```
   (A browser window will open — just sign in and you're done)

### Install This Plugin

Open your terminal and run these two commands:

```
claude plugin marketplace add mangollc/claude-seo-skill
claude plugin install seo-aeo-pro@claude-seo-skill
```

That's it. The SEO tools are now available everywhere on your computer.

---

## How to Use It

### Step 1: Open Claude Code

Open your terminal (or the terminal inside VS Code, Cursor, or any code editor) and type:

```
claude
```

### Step 2: Set Up Your First Client

```
/new-client "Joe's Plumbing"
```

Claude will ask you a few questions:
- What's the website URL?
- What type of business is it? (local, online software, online store, etc.)
- Who are 2-3 competitors?

### Step 3: Start Using Commands

Just type any command. Here are the most popular ones:

---

## All Commands

### Setting Up

| Type this | What it does |
|-----------|-------------|
| `/new-client "Business Name"` | Set up a new client for tracking |

### Analyzing Your Website

| Type this | What it does |
|-----------|-------------|
| `/audit https://yoursite.com` | Full website health check with a score out of 100 and a prioritized fix list |
| `/score-page https://yoursite.com/page "your keyword"` | Score a specific page's SEO (0-100) and tell you exactly what to fix |
| `/serp-preview https://yoursite.com/page` | Show what your page looks like in Google search results |
| `/cannibalization "client-name"` | Find pages on your site that compete against each other (hurting both) |
| `/content-decay "client-name"` | Find old content that needs updating |

### Finding Keywords

| Type this | What it does |
|-----------|-------------|
| `/keywords "plumber austin" --local` | Find keywords for a local business |
| `/keywords "project management" --saas` | Find keywords for an online software company |
| `/topic-map "client-name" "main topic"` | Plan your entire content strategy around a topic |

### Creating Content

| Type this | What it does |
|-----------|-------------|
| `/schema https://yoursite.com/page` | Generate structured data code (helps Google understand your page) |
| `/gbp-calendar "client-name"` | Create a full month of Google Business Profile posts, ready to copy-paste |

### AI Search Visibility

| Type this | What it does |
|-----------|-------------|
| `/aeo-check "Your Brand" "keyword1" "keyword2"` | Check if your brand shows up in AI search results (Google AI, Perplexity, ChatGPT) |
| `/brand-serp "Your Brand"` | See what appears when someone Googles your brand name |
| `/enhance-aeo "client-name" "topic"` | Deep AI question discovery — find what people ask LLMs, test AI visibility across all keywords, mine Reddit/Quora/PAA |

### Reporting

| Type this | What it does |
|-----------|-------------|
| `/report "client-name"` | Generate a professional monthly SEO report |

---

## Examples

### "I want to check if my website has SEO problems"

```
/audit https://mywebsite.com
```

You'll get:
- An overall health score (0-100)
- Category-by-category breakdown
- A prioritized list of fixes (most impactful first)

### "I want to find keywords my customers are searching for"

```
/keywords "emergency plumber austin" --local
```

You'll get:
- A list of keywords people actually search for
- How hard each keyword is to rank for
- Which keywords will bring the most revenue
- Groups of related keywords you should target together

### "I want to score a specific page"

```
/score-page https://mysite.com/services "plumber austin"
```

You'll get:
- A score out of 100
- Breakdown: title tag, meta description, headings, content depth, images, links, etc.
- The top 5 things to fix to improve your ranking

### "I need Google Business Profile posts for the month"

```
/gbp-calendar "joes-plumbing"
```

You'll get:
- 12-16 ready-to-publish posts for the entire month
- Mix of tips, offers, updates, and service highlights
- Each post includes suggested photos and calls-to-action

### "I want to know if AI search engines mention my brand"

```
/aeo-check "Joe's Plumbing" "best plumber austin" "emergency plumber near me"
```

You'll get:
- Whether your brand appears in Google AI Overviews
- Which competitors show up instead
- What to change so AI search engines recommend you

### "I want to know what people are asking AI chatbots about my industry"

```
/enhance-aeo "joes-plumbing" "emergency plumber"
```

You'll get:
- Every question people ask about your topic (mined from Google PAA, autocomplete, Reddit, and Quora)
- Which of your keywords trigger AI Overviews and whether you're cited
- Which competitors AI engines cite instead — and why
- A priority action plan: top questions to answer, pages to restructure, content gaps to fill

---

## 🔥 Enhanced AEO Discovery (`/enhance-aeo`)

**The most powerful command in the plugin.** This is how you find out what real people are asking AI chatbots — and make sure AI engines cite YOU in the answers.

### The Problem

You can't see what people ask ChatGPT, Perplexity, or Google AI. Those platforms don't share query data. So how do you optimize for something you can't measure?

### The Solution

People ask AI chatbots the same questions they search on Google, ask on Reddit, and type into Quora. `/enhance-aeo` mines ALL of those sources to reverse-engineer what people are asking AI — then tests whether you show up in AI answers.

### How to Run It

```
/enhance-aeo "client-name" "your main topic"
```

### What It Runs (5 Modules)

| Module | What it does | Why it matters |
|--------|-------------|----------------|
| **1. PAA Chain Mining** | Mines Google's "People Also Ask" boxes using what/how/why/vs patterns | PAA questions = the exact questions people ask ChatGPT and Perplexity |
| **2. Autocomplete Mining** | Scrapes Google autocomplete with 7 modifiers (how, best, for, can, should, is, a) | Autocomplete = real-time search behavior = what people type into AI chatbots |
| **3. Reddit & Quora Mining** | Finds actual questions on Reddit threads and Quora answers | LLMs are literally trained on this data — these questions ARE AI queries |
| **4. Question Tree Mapping** | Builds a full who/what/when/where/which/why map around your topic | Covers every angle people approach your topic from |
| **5. AI Visibility Testing** | Tests your top 20 keywords — checks if AI Overviews appear, if you're cited, who IS cited | Shows exactly where you're invisible to AI and why competitors win |

### What You Get Back

**Master Question List**
- Every question people ask about your topic — deduplicated across all 5 sources
- Ranked by frequency (appeared in multiple sources = highest priority)
- Tagged: source (PAA/Autocomplete/Reddit/Quora), intent (informational/commercial), status (answered on your site or not)

**AI Visibility Scorecard**

| Keyword | AI Overview? | You Cited? | Who's Cited Instead | Gap Level |
|---------|-------------|------------|---------------------|-----------|
| best plumber austin | Yes | No | competitor1.com | 🔴 High |
| emergency plumber near me | Yes | Yes | — | 🟢 None |
| plumber cost austin | No | — | — | ⚪ No AI Overview |

**Competitor Analysis**
- Which competitors get cited by AI and why
- What their content structure looks like vs yours
- Schema markup differences
- Content depth differences

**Priority Action Plan**
1. Top 10 questions to create content for (not yet answered on your site)
2. Top 5 pages to restructure for AI citation
3. Schema markup to add
4. Content gaps where competitors dominate AI results
5. Reddit/Quora communities to participate in for brand visibility

### No API Keys Needed

Everything runs on Firecrawl search — no Google Search Console, no Ahrefs, no paid tools. Just install and run.

---

## Works With Any Business Type

| Business Type | Example Commands |
|---------------|-----------------|
| **Local businesses** (plumbers, lawyers, dentists) | `/keywords "dentist chicago" --local` then `/gbp-calendar "client"` |
| **Online software (SaaS)** | `/keywords "project management tool" --saas` then `/topic-map "client" "project management"` |
| **Online stores** | `/audit https://store.com` then `/schema https://store.com/product` |
| **Blogs and content sites** | `/content-decay "client"` then `/score-page https://blog.com/post "keyword"` |

---

## Works In Any Editor

| Editor | How to use |
|--------|-----------|
| **Terminal** (Mac/Windows/Linux) | Open terminal, type `claude`, then use commands |
| **VS Code** | Open the built-in terminal (`` Ctrl+` ``), type `claude` |
| **Cursor** | Open the built-in terminal (`` Ctrl+` ``), type `claude` |
| **Windsurf** | Open the built-in terminal (`` Ctrl+` ``), type `claude` |
| **Any editor with a terminal** | Same — open terminal, type `claude` |

---

## Managing Multiple Clients

This plugin is built for agencies. You can manage as many clients as you need:

```
/new-client "Joe's Plumbing"
/new-client "Austin Dental Care"
/new-client "TechStart SaaS"
```

Each client gets their own folder with all their data:
- Keyword research
- Audit results
- Content scores
- GBP posts
- Backlink data
- Monthly reports

Switch between clients by using their name in any command:

```
/audit https://joesplumbing.com
/report "joes-plumbing"
/gbp-calendar "austin-dental-care"
/keywords "saas analytics" --saas
```

---

## What's Inside (6 Skill Areas)

### 1. Keyword Strategy
Find keywords that bring revenue, not just traffic. Different workflows for local businesses vs online companies. Includes competitor analysis, keyword grouping, and content planning.

### 2. Technical SEO Audit
Full website health check: page speed, mobile-friendliness, broken links, missing tags, schema markup, security headers, and 10+ other checks. Scored 0-100 with prioritized fixes.

### 3. Content Optimization
Score any page's SEO across 10 categories. Check readability, E-E-A-T (Google's quality signals), heading structure, keyword usage, image optimization, and more. Includes a pre-publish checklist for new content.

### 4. Local SEO
Everything for Google Business Profile: competitor research, post generation, 30-day posting calendars, review response templates, citation audits, and local keyword optimization.

### 5. Backlinks & Reporting
Reverse-engineer competitor backlinks into a 90-day outreach plan. Find toxic links, discover unlinked brand mentions, and generate professional monthly reports.

### 6. AI Search Optimization (AEO)
The newest frontier. Optimize your content to appear in Google AI Overviews, Perplexity answers, and ChatGPT responses. Includes entity optimization, structured data for AI, brand SERP management, and **Enhanced AEO Discovery** — mines real questions people ask AI chatbots from Google PAA, autocomplete, Reddit, and Quora, then tests your AI visibility keyword-by-keyword.

---

## Frequently Asked Questions

**Do I need to know SEO to use this?**
No. Just type the commands and Claude explains everything in plain language with specific action items.

**Does this cost money?**
The plugin itself is free and open source. You need a Claude Code subscription and a Firecrawl account (has a free tier).

**Can I use this for client work?**
Yes, it's built specifically for agencies managing multiple clients. Each client's data is kept separate.

**Does it actually change my website?**
No. It only analyzes and recommends. You (or your developer) make the actual changes.

**What websites can it analyze?**
Any public website. It works with WordPress, Shopify, Wix, custom sites — anything with a URL.

**How is this different from Semrush or Ahrefs?**
Those are subscription tools ($100-400/month). This plugin uses AI to perform similar analysis for free using publicly available data. It won't have exact search volume numbers, but it provides volume estimates and everything else you need.

---

## License

MIT — free to use, modify, and share.

## Contributing

Found a bug or have an idea? Open an issue or pull request on [GitHub](https://github.com/mangollc/claude-seo-skill).
