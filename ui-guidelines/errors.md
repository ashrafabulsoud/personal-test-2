# Errors Log

**Crawl Date:** 2026-03-16

| URL | Status | Reason | Timestamp |
|---|---|---|---|
| https://filamentphp.com/sitemap.xml | 404 | No sitemap available | 2026-03-16 |
| https://filamentphp.com/blog | 200 (redirect) | Resolved to /insights | 2026-03-16 |
| https://filamentphp.com/community | 200 (redirect) | Resolved to /insights | 2026-03-16 |

**Notes:**
- No sitemap.xml or sitemap_index.xml found; crawl proceeded via homepage link extraction
- `/blog` and `/community` routes redirect to `/insights`
- robots.txt exists but contains no sitemap pointer and has no disallow rules
- Font files (.woff2) referenced in CSS from `/build/assets/` path; not downloaded as they require the origin server
