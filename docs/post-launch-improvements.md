# Post-launch improvements

This document records useful work that should be revisited after the production
site is online and stable. These items do not need to delay the current DNS and
hosting launch.

## Quick accessibility fixes

- Add a semantic `<main>` landmark to:
  - About
  - Contact
  - Forum
  - Library
  - Newsletter
  - What Now?
  - Articles
  - Audio
  - Videos
  - Ebooks
- Remove leftover Grammarly markup and the duplicate `id="11"` attributes from
  the blog post *Enlightenment Is Not Worth Striving For*.
- Add an accurate `title` attribute to the YouTube iframe in the blog post
  *Just One Look Is All It Takes*.
- Change the first **Further Reading** heading on the About page from `h3` to
  `h2` so the heading sequence is logical.
- Add a clear `:focus-visible` treatment to homepage links.
- Increase mobile touch areas for navigation links, contextual back links, and
  the homepage legal links without changing their visual order or wording.

## Performance and asset cleanup

- Add lazy loading to the Zero owl image where it appears below the initial
  viewport.
- Confirm that `assets/brand/zero-pointing-right-nav.png` is unused, then remove
  it.
- Optimize the main Zero owl image while preserving its appearance and
  transparency.
- Review whether all locally stored personal-report MP3 files should remain in
  the repository over the long term. They currently total approximately 106 MB.

## Translated ebooks

- Inventory every translated ebook currently stored under `legacy-site/`.
- Do not edit or publish those files directly from `legacy-site/`.
- Copy approved editions into a permanent Library structure outside the legacy
  directory.
- Organize translations clearly by book title and language.
- Record, where known:
  - language and translated title;
  - translator;
  - edition and publication date;
  - source file;
  - copyright and reuse status;
  - whether the translation has been reviewed.
- Add approved translations to the Ebooks section with clear language labels.
- Check filenames, downloads, mobile presentation, and PDF accessibility.
- Add sitemap and canonical metadata for any new HTML landing pages.

## Historical podcast preservation

- Create a repository instruction document explaining that the existing
  Archive.org podcast collection is a complete historical series of 41
  episodes.
- Preserve existing episode numbers, titles, dates, audio files, and permanent
  Archive.org URLs.
- Do not silently rewrite or renumber the historical collection.
- Document the relationship between the historical names *The John Sherman
  Podcast* and *Being Human: The Just One Look Podcast*.
- Document how the website acts as the presentation layer for Archive.org
  audio, episode metadata, summaries, context, and navigation.
- Preserve a repository-controlled or local preservation copy where practical
  and consistent with storage policy.

## Instructions for any future podcast

If new episodes are produced, begin a clearly identified new series rather than
continuing the historical 41-episode sequence.

The publishing instructions should define:

- series title and purpose;
- episode-numbering convention;
- hosts, guests, and contributors;
- cover artwork;
- required episode metadata;
- audio format and quality;
- transcript requirements;
- copyright and licensing;
- Archive.org collection and item structure;
- website episode-page template;
- upload, publication, and verification workflow;
- how to update the series index and sitemap;
- how permanent URLs will be protected.

Published audio should not be replaced unless correcting a genuine technical
defect. Corrections should be documented.

## Larger accessibility work

- Consider equivalent transcripts for all 41 historical podcast episodes.
- Consider transcripts or equivalent text for the personal-report recordings.
- Verify caption availability and accuracy for the historical YouTube videos
  embedded in two blog posts.
- Review the accessibility of repository PDFs, prioritizing the principal
  method instructions and the most frequently used ebooks.

## Confirmed findings that require no correction

- The Just One Look Foundation concluded its work in 2025 and has been
  submitted for dissolution; the current About-page description is consistent
  with that history.
- The Videos page intentionally links to the official YouTube channel.
- Two historical blog posts contain embedded YouTube videos; only one currently
  lacks an accessible iframe title.
- Representative color-contrast checks passed.
- All inspected images have alternative text.
- All inspected links have accessible names.
- Podcast audio players provide browser controls and direct-MP3 fallback links.

## Working approach

- Recheck these findings against the production site after launch.
- Address quick fixes in small, focused pull requests.
- Preview and test desktop and mobile behavior before merging.
- Keep content migration and preservation-policy work separate from minor HTML
  and CSS corrections.
