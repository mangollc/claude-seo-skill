---
description: Set up a new client profile for multi-client SEO tracking
argument-hint: [client-name]
---

# New Client Setup

1. Ask the user for: client name, domain URL, business type (local/saas/ecommerce/publisher), industry, and 2-3 competitor domains
2. For local businesses, also ask for: business name, address, phone, service areas, services list
3. Generate a slug from the client name (lowercase, hyphens, no special chars)
4. Create the directory structure under `.seo/clients/{slug}/` with all subdirectories (keywords, technical, technical/schema-markup, content, content/page-scores, local, local/gbp-posts, local/gbp-posts/posts, backlinks, backlinks/competitor-profiles, aeo, reports)
5. Write the client config to `.seo/clients/{slug}/config.json` following the schema in [rules/client-setup.md](../skills/seo-keywords/rules/client-setup.md)
6. Create `.seo/config.json` if it doesn't exist, set this as the default client
7. Add `.seo/` to `.gitignore` if not already there
8. Run initial site discovery: `firecrawl map {domain} -o .seo/clients/{slug}/technical/sitemap-urls.txt`
9. Run homepage capture: `firecrawl scrape {domain} -o .seo/clients/{slug}/technical/homepage.md`
10. Display summary: client name, domain, pages discovered, business type, competitors listed
