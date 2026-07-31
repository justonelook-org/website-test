# Copy-paste task for the coworker

Paste the text below into Codex Desktop from a workspace that has access to the
old Just One Look hosting/DNS configuration and the GitHub repository.

---

We are preparing `justonelook.org` for migration from the existing host to the
GitHub Pages site in `justonelook-org/website-test`.

Please handle only the hosting, old-server, redirect, DNS, and GitHub Pages
cutover work described below. Do not rewrite the new site's content. Inspect
the current external configuration first, report what you find, and do not
change DNS or perform the final cutover until the proposed configuration and
redirect behavior have been reviewed.

## Current repository findings

- The intended publishing branch is `main`.
- The repository uses Jekyll `_config.yml` to exclude `legacy-site/`.
- There is currently no repository `CNAME`.
- There is no custom Pages Actions workflow, so confirm the actual Pages source
  in GitHub Settings > Pages.
- The repository now contains `privacy.html`, `terms.html`, `copyright.html`,
  `sitemap.xml`, and a Sitemap declaration in `robots.txt`.
- Canonical links, Open Graph URLs/images, social-card metadata, the sitemap,
  and robots declaration provisionally use `https://justonelook.org`. If `www`
  is chosen as canonical, run both `./scripts/Set-SiteMetadata.ps1 -BaseUrl
  https://www.justonelook.org` and `./scripts/New-Sitemap.ps1 -BaseUrl
  https://www.justonelook.org`, then update the Sitemap line in `robots.txt`
  before cutover.
- The inactive newsletter page is marked `noindex` until signup is implemented.
- The redirect proposal is in `launch/redirect-inventory.csv`.
- Redirect rows have these statuses:
  - `ready`: safe to prepare as a permanent redirect.
  - `review`: requires a decision before implementation.
  - `no-target`: do not redirect yet; the new destination is missing.
- Do not alter or remove `forum.justonelook.org`; it is a separate live service.

## Required investigation and proposed plan

1. Determine whether the production canonical hostname should be
   `https://justonelook.org` or `https://www.justonelook.org`.
2. Inspect GitHub Settings > Pages and report:
   - publishing source, branch, and folder;
   - current Pages deployment status and URL;
   - custom-domain setting;
   - domain-verification status;
   - HTTPS certificate and "Enforce HTTPS" status.
3. Inspect the current DNS records for the apex, `www`, and `forum` hostnames.
   Identify records that must change for GitHub Pages and records that must
   remain.
4. Inspect the old web server and determine the best way to issue real
   path-level `301` redirects after cutover. Prefer server/CDN redirects over
   HTML or JavaScript redirects.
5. Load `launch/redirect-inventory.csv` and validate every `ready` mapping
   against both the old URL and its proposed new URL.
6. For `review` and `no-target` rows, report the decision or missing dependency;
   do not silently substitute a destination.
7. Propose a policy for old route families that are not individually listed:
   - historical forum threads;
   - WordPress tags, authors, search, pagination, attachments, API/`wp-json`,
     comments, and feeds;
   - obsolete event, donation, volunteer, webinar, testimonial, report,
     international-language, and form URLs.
   Classify each family as preserve, redirect to a specific replacement,
   redirect to a relevant section, or return `410 Gone`. Avoid redirecting every
   unknown URL to the homepage.
8. Confirm how redirects will continue working after the old site's content is
   retired. DNS alone cannot perform path-level redirects.
9. Prepare, but do not yet execute, the exact cutover sequence:
   - lower DNS TTL if appropriate;
   - configure and verify the GitHub Pages custom domain;
   - install and test redirects;
   - change apex and `www` DNS records;
   - wait for TLS provisioning;
   - enable HTTPS enforcement;
   - verify canonical-host and HTTP-to-HTTPS redirects.

## Mandatory pre-cutover checks

- The Pages deployment must contain the new site and must not publish
  `legacy-site/`.
- Representative `/legacy-site/...` and `.php` requests must return `404` or
  `410`; PHP source must never be served.
- The custom `404.html` must be returned with HTTP status 404.
- Both apex and `www` must resolve predictably to one canonical hostname.
- `http://` must redirect to `https://`.
- `forum.justonelook.org` must continue to resolve and operate independently.
- Test a sample of homepage, Library, Blog, Podcast, ebook/PDF, Archive.org
  audio, Forum, legal, and newsletter destinations.
- Confirm that the approved privacy, terms, and copyright wording still matches
  the ownership and services in effect on the launch date.
- Test representative redirects from each route family, including query
  strings where relevant.
- Check for redirect loops and multi-hop redirect chains.

## Deliverable

Return a focused report containing:

1. current GitHub Pages, DNS, TLS, and old-server state;
2. the chosen canonical hostname;
3. the exact proposed DNS record changes;
4. the redirect mechanism and validated redirect list;
5. unresolved decisions or missing destinations;
6. a reversible, ordered cutover and rollback plan;
7. a post-cutover verification checklist.

Do not perform the final DNS cutover until this report has been reviewed.

---
