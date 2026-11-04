---
name: find-viral-videos
description: Find viral TikToks and Instagram Reels in the Viral Swipe File library by niche, format, brand, platform or creator, and quote each video's hook, views and viral factor with its link. Use when the user asks for viral videos or examples, what's working in a niche or format, videos that beat their account's usual views, the top videos in a niche, or a creator's best videos.
---

# Find and cite viral videos

Explicit user instructions take priority over this workflow.

## 1. Resolve names to slugs

`list_videos` filters on niche and format slugs. Plain names usually work
("Make Money Online" becomes `make-money-online`), but when a name is not an
exact niche or format:

- call `search_library` with the user's words, or
- call `list_niches` / `list_formats` and pick the closest match. They do
  not count toward the team's daily questions, so use them freely.

For an app or brand (one featured in the videos), call `list_brands` and
pass its slug as `brand`. A brand that is not listed has too few videos in
the library: say so rather than guessing.

If two niches fit, say which one you used. If nothing fits, say so and use
`search` (2 to 4 plain words over hook, caption, description, niche, formats
and creator; no OR, AND or quotes) instead of guessing a slug. Niches are a
closed list, so a topic like "home decor" is a `search`, with no `niche`.

## 2. Pick the tool

| Question | Tool |
| --- | --- |
| A topic, brand or creator name, no exact slug | `search_library` |
| Top videos in a niche, format, platform or period | `list_videos` (`sort: "viral"` by default) |
| Most-viewed rather than most outsized | `list_videos` with `sort: "views"` |
| Newest additions | `list_videos` with `sort: "recent"` |
| One creator's best videos | `list_videos` with `creator` |
| Videos made a certain way (a UGC selfie, an app mockup, a hook tactic, a tone) | `list_videos` with `visual_format`, `hook_tactic`, `tone`, `emotional_trigger`, `talent`, `awareness` or `asset_type`. Only videos the classifier has read match; each card shows its own labels |
| What worked for one app or brand: its hooks, formats, creators | `get_brand`, then `list_videos` with `brand` |
| Which apps and brands the library covers | `list_brands` |
| One video's full hook and description (lists already carry the hook) | `get_video` |
| Which niches or formats exist, and how many videos each has | `list_niches`, `list_formats` |
| The user's team's saved videos | `list_saved_videos` |

Page with `offset` (use the returned `nextOffset`). A null `nextOffset` means
there is no further page for this account: narrow with filters or search
words instead, and pass on any `note` the answer carries. `min_viral_factor` keeps
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
- A missing figure is unavailable, not zero.
- If a call answers with a message instead of results, saying the team has
  used today's questions, pass it on as given, with when the count starts
  again, and do not retry before then. It is not an error to work around.

## 4. Stop at the edge of the data

Decline, and say why, for live trends, the user's own account analytics,
YouTube or long-form video, and downloading or reposting someone's video.
Offer the closest thing the library holds. Never invent a video, a hook or a
figure the tools did not return.
