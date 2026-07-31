# Production launch handoff

This directory contains repository-derived launch material for coordinating the
move from the existing site to GitHub Pages.

## Redirect inventory

Run:

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ./scripts/New-RedirectInventory.ps1
```

The generated `redirect-inventory.csv` uses three statuses:

- `ready`: repository inspection found a clear old-to-new mapping.
- `review`: the proposed destination or retirement policy needs a human decision.
- `no-target`: the new site does not yet contain a destination.

The current generated inventory has no `no-target` rows. The remaining review
rows concern the inactive newsletter and the policy for historical forum entry
points.

The inventory deliberately concentrates on stable top-level URLs, the old
WordPress Blog/Podcast routes, and all dated posts represented in the new site.
It does not automatically redirect every historical forum thread, WordPress
API endpoint, tag, author, search, comment feed, or attachment URL. Those large
route families need an explicit preserve, archive, `410 Gone`, or fallback
policy from the person controlling the old server.

## Legacy publication safety

Run:

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ./scripts/Test-LegacyPublication.ps1
```

This checks the repository guardrails. It cannot prove what GitHub Pages
actually published without an artifact directory. For final verification:

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ./scripts/Test-LegacyPublication.ps1 -PublishedDirectory <artifact-directory>
```

The final check must pass before DNS cutover. Representative deployed legacy
URLs should also be requested directly and must return `404` or `410`, never
source code or archived pages.

## Coworker handoff

`coworker-codex-task.md` contains a self-contained task that can be pasted into
Codex Desktop by the person who controls the old host, DNS, and GitHub Pages
settings. It deliberately tells that agent to inspect and propose the cutover
before changing DNS.

## Canonical hostname

The sitemap and robots declaration provisionally use
`https://justonelook.org`. If the final canonical host is `www`, regenerate:

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ./scripts/New-Sitemap.ps1 -BaseUrl https://www.justonelook.org
```

Then update the Sitemap line in `robots.txt`. The legal pages are practical
repository drafts based on current site behavior and must be approved by the
site owner; they are not legal advice.

Canonical and social-share URLs are generated separately:

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ./scripts/Set-SiteMetadata.ps1 -BaseUrl https://www.justonelook.org
```

If the canonical host changes, run both generators with the same `BaseUrl` and
update `robots.txt`.
