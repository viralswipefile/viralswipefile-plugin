# Viral Swipe File plugin

Viral TikToks and Instagram Reels for Claude, ChatGPT, Codex, Cursor and Grok:
search a library of short-form videos that went viral, by niche, format and
creator, and read each video's hook, caption, views, engagement and viral
factor.

[Viral Swipe File](https://viralswipefile.com) files each video under a niche
and one or more formats (selfie with background, face close-up, story in
slideshow and more). **Viral
factor** is how many times more views a video got than its account usually
gets, so sorting by it finds outliers whatever the account's size.

This plugin connects your AI assistant to the library over MCP and adds skills
that tell it how to find, quote and learn from the videos.

## What you can ask

- "Show me the most viral fitness videos and the hooks behind them."
- "Which video formats work best for astrology apps on TikTok?"
- "Write 5 hooks for my budgeting app, modelled on viral finance videos."
- "What are this creator's best-performing videos?"
- "Turn my team's saved videos into a UGC brief."

## What is in here

| Path | |
| --- | --- |
| `.claude-plugin/plugin.json` | Claude plugin manifest |
| `.claude-plugin/marketplace.json` | Marketplace entry, so this repo can be added as a Claude Code marketplace |
| `.mcp.json` | The remote MCP server, `https://viralswipefile.com/api/mcp` |
| `skills/` | Five skills: get started, find viral videos, write hooks, research a niche, brief from saved videos |
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
term, are sent to that server. Viral Swipe File counts each call against your
team's usage, with the AI client's name, and records it in its product
analytics (PostHog): the tool name, its arguments, timing, errors, your
account identifier and the AI client's name and version. It does not record
what the tool returned. Nothing else from your conversation or your machine is
sent. See the [privacy policy](https://viralswipefile.com/privacy).

## Scope

A library of past viral videos, not a live trend feed. TikTok and Instagram
Reels only, not YouTube or long-form video. No analytics for your own
account. It links to videos and never downloads or reposts them.

## Support

[viralswipefile.com/contact](https://viralswipefile.com/contact) or
hello@viralswipefile.com.
