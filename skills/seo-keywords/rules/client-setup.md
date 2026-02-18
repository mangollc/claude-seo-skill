---
name: seo-client-setup
description: |
  How to initialize and manage client profiles for multi-client SEO work.
  Referenced by all SEO skills for loading client context.
---

# Client Setup & Management

## Directory Structure

Create `.seo/` in the working directory if it doesn't exist. Add `.seo/` to `.gitignore`.

```
.seo/
├── config.json                    # Global agency config
└── clients/{slug}/
    ├── config.json                # Client profile
    ├── keywords/
    ├── technical/
    │   └── schema-markup/
    ├── content/
    │   └── page-scores/
    ├── local/
    │   └── gbp-posts/
    │       └── posts/
    ├── backlinks/
    │   └── competitor-profiles/
    ├── aeo/
    └── reports/
```

## Global Config: `.seo/config.json`

```json
{
  "default_client": "client-slug",
  "agency_name": "Your Agency",
  "report_branding": {
    "header": "Monthly SEO Report",
    "footer": "Prepared by Your Agency"
  },
  "preferences": {
    "output_format": "json",
    "report_format": "markdown"
  }
}
```

## Client Config: `.seo/clients/{slug}/config.json`

```json
{
  "name": "Client Display Name",
  "slug": "client-slug",
  "domain": "https://example.com",
  "business_type": "local|saas|ecommerce|publisher",
  "industry": "plumbing",
  "service_areas": ["Austin, TX", "Round Rock, TX"],
  "target_audience": "Homeowners needing emergency plumbing",
  "competitors": [
    { "name": "Competitor A", "domain": "https://competitor-a.com" },
    { "name": "Competitor B", "domain": "https://competitor-b.com" }
  ],
  "gbp": {
    "business_name": "Example Plumbing",
    "address": "123 Main St, Austin, TX 78701",
    "phone": "(512) 555-1234",
    "categories": ["Plumber", "Water Heater Installation"],
    "services": ["Drain Cleaning", "Water Heater Repair", "Pipe Repair"]
  },
  "brand_keywords": ["Example Plumbing", "Example"],
  "target_keywords": [],
  "languages": ["en"],
  "regions": ["US"],
  "created_at": "2026-02-16",
  "notes": ""
}
```

### Required Fields

All clients must have: `name`, `slug`, `domain`, `business_type`, `industry`, `competitors` (min 2).

### Optional Fields

- `gbp` — required only for local/service businesses
- `service_areas` — required for local businesses
- `languages` / `regions` — required for international SEO
- `target_keywords` — populated after keyword research

## Loading Client Context

Every skill workflow should start by:

1. Check if `.seo/` exists. If not, ask user to run `/new-client` first.
2. If a client slug is provided, load `.seo/clients/{slug}/config.json`.
3. If no slug is provided, check `.seo/config.json` for `default_client`.
4. If no default, list available clients from `.seo/clients/` and ask user to choose.

## Creating a Client Slug

Convert client name to lowercase, replace spaces with hyphens, remove special characters:
- "Joe's Plumbing Co." → `joes-plumbing-co`
- "TechStart SaaS" → `techstart-saas`

## Initial Setup Steps

After creating the client config:

1. Run `firecrawl map {domain} -o .seo/clients/{slug}/technical/sitemap-urls.txt` to discover all URLs
2. Run `firecrawl scrape {domain} -o .seo/clients/{slug}/technical/homepage.md` to capture homepage
3. Count total pages: `wc -l .seo/clients/{slug}/technical/sitemap-urls.txt`
4. Display summary: client name, domain, total pages found, business type
