---
name: brief-from-saved-videos
description: Read the videos the user's team saved on Viral Swipe File and turn them into a content or UGC brief - shared hooks, formats and creators, and ideas to shoot next. Use when the user mentions their saved videos, a board, favourites, their swipe file or swipe folder on Viral Swipe File, or wants to turn saved inspiration into posts.
---

# Brief from saved videos

Explicit user instructions take priority over this workflow.

1. Call `list_saved_videos`. Page with `nextOffset` if the user wants all of
   them. If the list is empty, say the team has saved nothing yet and that
   videos are saved on viralswipefile.com; offer to find viral videos in
   their niche instead.
2. Summarise what the saved videos share: niches, formats, platforms and
   recurring hook patterns, each with counts from the list and a linked
   example.
3. Read the two or three strongest by viral factor with `get_video` for
   their full hook and caption.
4. Write the brief the user asked for: what to shoot, which hook pattern and
   format to use, and the saved video to reference for each idea.

The plugin is read-only: it cannot save, remove or reorder videos. Point the
user to viralswipefile.com for that.
