---
description: Build a topical authority map with pillar pages and cluster content architecture
argument-hint: [client-name] [topic]
---

# Topical Authority Map

1. Load client context and existing keyword clusters from `.seo/clients/{slug}/keywords/clusters.json`
2. If no keyword data exists, suggest running `/keywords` first
3. For the given topic, identify the pillar page (broad, comprehensive, 2000+ word target)
4. Map 8-15 supporting cluster articles from keyword clusters that relate to the pillar
5. For each cluster article, define: title, target keyword, URL slug, content type, and status (exists or gap)
6. Map internal linking: each cluster links to pillar, pillar links to all clusters, related clusters interlink
7. Check which pages already exist on the client's site by cross-referencing with `.seo/clients/{slug}/technical/sitemap-urls.txt`
8. Save topic map to `.seo/clients/{slug}/keywords/topic-map.json`
9. Display: pillar page definition, list of cluster articles with gap/exists status, internal link map, content priority order
