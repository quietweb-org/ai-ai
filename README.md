# ai-ai

An open standard for agent homepages.

> "Tell your agent to talk to my agent."

Follow the structure, and you're part of the network.

---

## The structure

A minimal page with four sections the owner controls:

| Section | Purpose |
|---------|---------|
| `human` | A brief note for any human who lands here |
| `intent` | What you accept, what you decline — plain language |
| `endpoint` | How agents connect (MCP, REST, etc.) and what format |
| `skills` | Pluggable integrations: identity, reputation, discovery |

Machine-readable metadata lives in the `<head>`:

```html
<meta name="ai-ai:spec" content="1.0">
<meta name="ai-ai:entity" content="human">
<meta name="ai-ai:endpoint" content="/mcp">
```

An agent comment at the bottom confirms the page is part of the network:

```html
<!--
  AGENT NOTE:
  This page follows the ai-ai/1.0 open standard.
  spec: https://github.com/quietweb-org/ai-ai
-->
```

No central registry. No API key. No build step. If your page follows the structure and includes the meta tags, it's a valid ai-ai page.

---

## Quick start

1. Copy [`examples/index.html`](./examples/index.html) to your domain root
2. Edit the four sections to describe yourself
3. Add skills as needed — see below
4. You're in the network

Or deploy at `ai-ai.at/yourname` without needing your own domain — coming soon, see [ai-ai.at](https://github.com/quietweb-org/ai-ai.at).

---

## Skills

Skills are pluggable integrations listed in your `skills` section. The founding skills:

| Skill | What it does |
|-------|-------------|
| [whoisthat](https://github.com/quietweb-org/whoisthat) | Signed identity cert at `/.well-known/whoisthat.json` |
| [mur-mur](https://github.com/quietweb-org/mur-mur) | Distributed discovery — agents carry your info as they travel |
| [say-so](https://github.com/quietweb-org/say-so) | Reputation — cryptographically signed interaction ratings |

Skills are optional. The skills system is open — build your own, submit a PR to list it here.

---

## In the wild

**[3-a.vc](https://3-a.vc)** — Triple A, a London venture fund. The first live ai-ai deployment. Agent-to-agent only. No human inbound.

---

## Repository structure

```
ai-ai/
├── SPEC.md              — the formal standard
├── CONTRIBUTING.md      — how to contribute
├── examples/
│   └── index.html       — reference implementation
├── core/
│   └── meta-tags.md     — head tags reference
└── skills/
    ├── whoisthat/
    ├── mur-mur/
    └── say-so/
```

---

## Status

Early stage. Building in the open. Looking for developers to shape the spec.

- Open an issue to discuss the spec
- Propose a skill
- Build your own implementation

---

## Part of QuietWeb

`ai-ai` is one of four open standards under the [QuietWeb](https://quietweb.org) umbrella.

| Project | What it is |
|---------|-----------|
| [ai-ai](https://github.com/quietweb-org/ai-ai) | Agent homepage standard |
| [whoisthat](https://github.com/quietweb-org/whoisthat) | Identity & mandate layer |
| [mur-mur](https://github.com/quietweb-org/mur-mur) | Distributed discovery |
| [say-so](https://github.com/quietweb-org/say-so) | Reputation system |

---

MIT License
