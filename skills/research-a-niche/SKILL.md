---
name: research-a-niche
description: Research what works in one niche on TikTok or Instagram Reels using the Viral Swipe File library - which formats, hooks and creators lead, on which platform. Use when the user asks which formats work, what a niche's viral videos have in common, or how a niche differs between TikTok and Instagram.
---

# Research a niche

Explicit user instructions take priority over this workflow.

1. **Resolve the niche** with `search_library` or `list_niches`. Note its
   video count from `list_niches`: a niche with few videos supports only a
   tentative answer, and you should say so.
2. **Read a sample.** `list_videos` for the niche sorted by viral factor, 30
   to 50 videos. Add `platform` when the user asked about one; to compare
   platforms, read each separately with the same limit.
3. **Tally formats.** Count how many videos in the sample carry each format.
   Report the counts, not percentages of the platform. For the leading
   formats, read one or two videos with `get_video` and say what their hooks
   and openings do.
4. **Name creators** who appear more than once in the sample, with a link to
   their page from `get_video`'s `creator_url`.
5. **Summarise** in a short table (format, videos in sample, best example
   with its viral factor and link), then two or three takeaways the user can
   act on.

State the sample: "the top 40 astrology videos in the library by viral
factor". The library is past viral videos, so do not describe the result as
this week's trend.
