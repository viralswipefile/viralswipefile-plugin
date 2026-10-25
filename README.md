# Viral Swipe File plugin

Know what to post next on TikTok and Instagram Reels. This plugin connects
Claude, ChatGPT, Codex, Cursor and Grok to a curated library of short-form
videos that went viral, filed by niche and format, so your assistant writes
hooks and content ideas from real posts. Each video comes with its hook,
caption, views, engagement and viral factor, and a link to watch it.

[Viral Swipe File](https://viralswipefile.com) files each video under a niche
and one or more formats (selfie with background, face close-up, story in
slideshow and more). **Viral factor** is how many times more views a video
got than its account usually gets: x10 is ten times its usual, so a small
account's breakout ranks next to a big one's.

The plugin reaches the library over MCP and adds skills that tell your
assistant how to find, quote and learn from the videos.

## What you can ask

- "What should I post this week for a fitness client?"
- "Show me the viral hooks in finance, then write 5 for my budgeting app."
- "Which video formats work best for astrology on TikTok?"
- "What are this creator's best videos?"
- "Turn my team's saved videos into a UGC brief."

The server also offers five ready-made prompts: what to post next, viral
hooks in my niche, swipe a creator's best videos, hooks for my product or
client, and formats that work in a niche. In Claude, open a chat's + menu and
pick Viral Swipe File.

## What is in here

| Path | |
| --- | --- |
| `.claude-plugin/plugin.json` | Claude plugin manifest |
| `.claude-plugin/marketplace.json` | Marketplace entry, so this repo can be added as a Claude Code marketplace |
| `.mcp.json` | The remote MCP server, `https://viralswipefile.com/api/mcp` |
| `skills/` | Six skills: get started, what to post, find viral videos, write hooks, research a niche, brief from saved videos |
| `plugin.json`, `mcp.json` | The same plugin in the [Agent Plugins](https://agent-plugins.org) format, for ChatGPT |
| `.codex-plugin/` | Codex and OpenAI Agents API manifest |
| `.cursor-plugin/` | Cursor manifest and marketplace entry |
| `.grok-plugin/` | Grok manifest |
| assets folder | Icon and logo |

The skills are plain Markdown instructions. The plugin ships no scripts, hooks
or executables and installs no packages.

## Install

**Claude Code**

```bash
claude plugin marketplace add viralswipefile/viralswipefile-plugin
claude plugin install viralswipefile@viralswipefile
```

**Codex** reads `.codex-plugin/plugin.json`. **ChatGPT** uses the root
`plugin.json` and `mcp.json`.

**Cursor**: add this repository from the Cursor plugin marketplace, or point
Cursor at it as a plugin repository.

**Grok**: `grok` loads it from `~/.grok/plugins/`, or pass the cloned
repository with `--plugin-dir`.

**Any MCP client, without the skills**

```bash
claude mcp add --transport http viralswipefile https://viralswipefile.com/api/mcp
```

On claude.ai, add `https://viralswipefile.com/api/mcp` as a custom connector.

## Sign-in and the data it sends

Connecting opens a browser sign-in to your Viral Swipe File account (OAuth
2.1). There is no API key to copy. The plugin requests read access to the
library and to the videos your team saved on the site. Every tool is
read-only: it cannot save, remove or post anything.

The plugin talks to one server, `viralswipefile.com`. When your assistant
calls a tool, the tool's arguments, such as a niche, a format or a search
term, are sent to that server. Viral Swipe File counts each call (except
`list_niches` and `list_formats`) against your team's usage, with the AI
client's name, and records every call in its product
analytics (PostHog): the tool name, its arguments (an argument containing an
email address or a phone or card number is replaced first), timing, how the
call turned out (how many results, or that nothing matched, the call was
refused or it failed), errors, your account identifier and the AI client's
name and version. Calls made close together are grouped into a session (for
ChatGPT, by the anonymous conversation id it sends). It does not record what
the tool returned, only how many results. Nothing else from your conversation
or your machine is sent. See the [privacy
policy](https://viralswipefile.com/privacy).

## Scope

A library of past viral videos, not a live trend feed. TikTok and Instagram
Reels only, not YouTube or long-form video. No analytics for your own
account. It links to videos and never downloads or reposts them.

## Support

[viralswipefile.com/contact](https://viralswipefile.com/contact) or
hello@viralswipefile.com.
