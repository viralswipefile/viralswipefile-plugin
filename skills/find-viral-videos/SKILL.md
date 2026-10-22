---
name: find-viral-videos
description: Find viral TikToks and Instagram Reels in the Viral Swipe File library by niche, format, platform or creator, and quote each video's hook and stats with its link. Use when the user asks for viral videos, examples, outliers, top videos in a niche or format, or a creator's best-performing videos.
---

# Find and cite viral videos

Explicit user instructions take priority over this workflow.

## 1. Resolve names to slugs

`list_videos` filters on niche and format slugs. Plain names usually work
("Make Money Online" becomes `make-money-online`), but when a name is not an
exact niche or format:

- call `search_library` with the user's words, or
- call `list_niches` / `list_formats` and pick the closest match.

If two niches fit, say which one you used. If nothing fits, say so and use
`search` (free text over hook, caption, niche, formats and creator) instead
of guessing a slug.

## 2. Pick the tool

| Question | Tool |
| --- | --- |
| A topic, brand or creator name, no exact slug | `search_library` |
| Top videos in a niche, format, platform or period | `list_videos` (`sort: "viral"` by default) |
| Most-viewed rather than most outsized | `list_videos` with `sort: "views"` |
| Newest additions | `list_videos` with `sort: "recent"` |
| One creator's best videos | `list_videos` with `creator` |
| One video's full hook and caption | `get_video` |
| Which niches or formats exist, and how many videos each has | `list_niches`, `list_formats` |
| The user's team's saved videos | `list_saved_videos` |

Page with `offset` (use the returned `nextOffset`). `min_viral_factor` keeps
only outliers, for example 4 or more. If a `days` window returns nothing,
say so and widen it; the library holds past viral videos, so recent windows
can be thin.

## 3. Quote every video with its basis

For each video you show:

- the hook, exactly as returned (do not paraphrase it as a quote),
- the platform and creator,
- views and viral factor, and engagement rate when relevant,
- the video's `url` on viralswipefile.com, so the reader can watch it.

Then:

- Explain viral factor once: views relative to the account's usual. A viral
  factor of 10 means ten times the account's normal views.
- A list is a sample of the library, not the whole platform. Say "in the
  library", never "on TikTok".
- When you count formats or patterns, give the counts from the videos you
  read ("6 of the 20 top fitness videos are face close-up").
- If a result has no `hook` and carries a `notice`, pass the notice on as
  given, without adding to it, when the user wants hooks.
- A missing figure is unavailable, not zero.

## 4. Stop at the edge of the data

Decline, and say why, for live trends, the user's own account analytics,
YouTube or long-form video, and downloading or reposting someone's video.
Offer the closest thing the library holds. Never invent a video, a hook or a
figure the tools did not return.
