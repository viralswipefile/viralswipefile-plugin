---
name: get-started
description: Set up Viral Swipe File after installation, check its connection when asked, and help the user try a first question. Use for get started, onboarding, setup, connection checks, or questions about what the library holds and what it can do.
---

# Get started with Viral Swipe File

Explain the plugin in a few sentences, then offer one concrete question to try.
Explicit user instructions take priority over this guidance.

## Choose the requested path

- For "set up", "get started" or "is it connected", call `list_niches` once.
  If it returns niches, the connection works: say so and name a few niches
  from the result. Do not list them all.
- If tools are unavailable or authentication fails, say the connection is not
  verified and tell the user to connect or reconnect Viral Swipe File in their
  app, signing in with their Viral Swipe File account. Do not claim the plugin
  is ready because this skill loaded.
- For "what can it do", explain without calling a tool.
- If the user already asked a real question, answer it with the
  find-viral-videos workflow instead of stopping at a suggestion.

## What to say

- Viral Swipe File is a library of TikToks and Instagram Reels that went
  viral, each filed under a niche and one or more formats (selfie with
  background, face close-up, story in slideshow and more).
- Each video has its hook, caption, creator, views, engagement rate and
  viral factor.
- **Viral factor** is how many times more views a video got than its account
  usually gets. Sorting by it finds outliers whatever the account's size.
- Every tool is read-only. Signing in also lets it read the videos the
  user's team saved on viralswipefile.com.

## What it cannot do

Say so plainly if asked: it is a collection of past viral videos, not a live
trend feed; it has no analytics for the user's own account; it covers TikTok
and Instagram Reels only; it links to videos and never downloads or reposts
them; it cannot save or remove videos.

## Suggested first questions

Offer one, adapted to what the user mentioned:

- "Show me the most viral fitness videos and the hooks behind them."
- "Which video formats work best for astrology apps on TikTok?"
- "Write 5 hooks for my app, modelled on viral videos in its niche."
- "What has my team saved, and what do those videos have in common?"

Never quote a figure from memory; figures come only from tool results.
