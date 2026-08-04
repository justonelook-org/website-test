# Just One Look Website: Purpose, Structure, and Guiding Principles

## Purpose of the new site

The new Just One Look website exists to keep John Sherman’s work available, understandable, and usable over the long term.

The site is not intended to become a large organization, a spiritual community, or a complicated online platform. Its primary purposes are to:

- Give visitors a direct opportunity to try the act of looking at themselves.
- Explain the method in clear, ordinary language.
- Provide practical guidance for what may follow the first look.
- Preserve the historical writings, talks, recordings, and publications associated with the work.
- Give people a separate place to discuss their experiences and the source material.

The site should remain useful even for a visitor who knows nothing about John Sherman or the history of Just One Look.

## The central visitor journey

The most important design decision is that the invitation to **Try It** comes before extensive explanation.

Just One Look is based on a simple act that must be attempted directly. The website should therefore avoid making visitors study a theory, adopt a belief, or understand the entire history before trying it.

The intended journey is:

1. Encounter a clear invitation to look at yourself.
2. Try the act directly.
3. Continue to **What Now?** for guidance about the recovery period and the use of self-directed attention.
4. Explore the background, history, and Library only when more context is wanted.
5. Use the Forum for questions, reports, and discussion.

The site should consistently favor direct experience over persuasion.

## How the method is presented

The website presents Just One Look as a practical psychological method, not as a religion, philosophy, meditation system, or spiritual identity.

The central distinction is between:

- The immediate act of looking inward at the felt sense of being “me.”
- The period of recovery from old protective psychological patterns that may follow.
- Self-directed attention as a practical aid during that recovery.

The site should avoid mystical language and unnecessary abstraction. It should not claim that the self is an illusion or ask visitors to achieve a special state of consciousness. The language should remain concrete, restrained, and focused on what the visitor can actually do.

## Design principles

The visual design is intentionally quiet, open, and minimal. The method is simple, and the website should not make it appear complicated.

Important principles include:

- Generous space and limited visual noise.
- Clear typography and short, readable sections.
- A restrained blue visual language derived from the established Just One Look identity.
- Minimal decorative elements and no unnecessary animation.
- Strong mobile usability.
- Accessibility through readable contrast, semantic structure, and simple navigation.

The blue line is used as a light structural element rather than heavy decoration.

The owl, called **Zero**, is a friendly guide and identifying symbol. Zero makes the site feel approachable without turning the method into a brand personality or fictional teaching voice. The owl’s eyes also echo the “oo” in the name and the simple invitation to look.

## Information architecture

The homepage provides the primary journey into the method. It should not try to summarize the entire archive.

The invitation to **Try It** appears before the footer and comes first in the overall visitor journey. The footer then continues that journey in this order:

- What Now?
- About
- Library
- Forum
- Newsletter
- Contact

Legal and administrative pages are visually separated from this main journey because they support the site but are not part of the method itself.

The **Library** is the permanent home for source and reference material. Its categories remain distinct because they serve different purposes:

- The Natural State Blog
- Being Human Podcast
- Audio
- Videos
- Articles
- Ebooks

These categories should not be merged merely to reduce the number of pages. Clear categories make a large historical collection easier to understand and maintain.

## Historical context

The website preserves work created over many years by John Sherman and Carla Sherman, including material previously published by the Just One Look Foundation.

The Just One Look Foundation concluded its work in 2025 and has been submitted for dissolution. The new site should not give the impression that the former organizational structure continues behind the present project. The present project is a continuation of access to the work, not a recreation of the old organization.

Historical material should be preserved faithfully, while introductions, navigation, and explanatory pages may use clearer contemporary language.

The site should distinguish carefully between:

- John Sherman’s original work and historical publications.
- Later editorial explanations and site navigation.
- New material created by the current Just One Look team.

## Repository and Forum relationship

The GitHub repository contains stable publications, website pages, media references, and project documentation.

Discussion belongs in the external Discourse Forum.

Blog posts, podcast episodes, and Library sections may direct readers to relevant Forum areas, but the static website should not acquire its own:

- Comment system
- User accounts
- Discussion database
- Membership platform
- Custom social features

This separation keeps the published site simple, private, inexpensive, and maintainable.

## Technical structure

The site is built from static HTML and shared CSS and is published through GitHub Pages.

The production setup includes:

- The canonical Just One Look domain.
- HTTPS.
- A GitHub Pages `CNAME`.
- Canonical page URLs.
- Social-sharing metadata.
- `sitemap.xml`.
- `robots.txt`.
- Deliberate 404 behavior.
- Shared navigation and reusable layout, typography, and metadata patterns.

Permanent URLs should be kept stable wherever possible.

The `legacy-site/` directory is retained as a historical and migration source. It must not be included in the published website.

Repository responsibilities should remain separate from domain registration, DNS, Archive.org, YouTube, Forum administration, newsletter services, and other external systems.

## Media preservation

The existing podcast is preserved as the complete **41-episode historical collection** of *Being Human: The Just One Look Podcast*, formerly *The John Sherman Podcast*.

Archive.org is the long-term preservation and media-hosting location for this historical collection. The website remains the presentation layer, providing titles, summaries, metadata, context, and access to the recordings.

Any future podcast production should begin as a new series rather than silently extending or rewriting the historical 41-episode collection.

Other media is handled according to its purpose:

- Personal-report audio is currently stored locally in the repository.
- Videos remain on the official YouTube channel.
- Articles and ebooks are preserved as repository PDFs.
- Translated ebooks still located in `legacy-site/` should be migrated gradually into the active Library structure.

Preservation should take priority over redesigning historical material.

## Maintenance principles

Future work should follow these principles:

- Keep permanent links stable.
- Prefer small, focused branches and pull requests.
- Avoid unnecessary JavaScript, frameworks, services, databases, and dependencies.
- Preserve source material before changing presentation.
- Keep the site usable on mobile devices and slower connections.
- Consider privacy and accessibility before adding any external service.
- Do not add features merely because they are common on modern websites.
- Keep explanatory language consistent across the homepage, method pages, Library, bots, and Forum.
- Clearly document decisions that affect the site’s long-term structure.

The site should remain modest enough that future caretakers can understand and maintain it without specialist infrastructure.

## Overall standard

Every addition should be tested against three questions:

1. Does this help a person try or understand Just One Look?
2. Does this help preserve or navigate the source material?
3. Does this make the site meaningfully easier to use without adding unnecessary complexity?

When the answer to all three is no, the addition probably does not belong on the site.
