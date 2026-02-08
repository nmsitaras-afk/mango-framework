# 🥭 MANGO Framework

**Multi-Agent Neural Governance Organization**

> Orchestration tells agents how to talk. Governance tells agents what to focus on.

MANGO is a governance and identity framework for AI agent systems. It reverse-engineers Steve Jobs' Apple (1997–2011) — one of the most successful organizational structures in business history — into a reusable architecture for coordinating AI agents.

## The Problem

Every AI agent framework (CrewAI, AutoGen, LangGraph, Swarm) solves the same thing: **orchestration** — how agents communicate, route tasks, and share state.

None of them solve: **governance** — how do you organize agents so they actually produce good work? How do you prevent a swarm from becoming a committee?

## The Answer: 6 Principles from Apple

| # | Principle | In Practice |
|---|-----------|-------------|
| 1 | **Spoke-and-Wheel** | All decisions route through one hub. No committees. |
| 2 | **Demo Culture** | Ship outputs, not status reports. |
| 3 | **DRA System** | One Directly Responsible Agent per task. No ambiguity. |
| 4 | **NO > YES** | Focus is saying no to the hundred good ideas. |
| 5 | **State-Based Continuity** | Files are memory. Text > Brain. Always. |
| 6 | **Apple Alignment Filter** | "Does this serve the mission? Is this the best version?" |

---

## 🤝 The Teammate System

MANGO's core innovation: **pre-built specialist identities** you can deploy as agents. Each teammate has a defined role, communication style, and operational boundaries.

### Core Team (your starting lineup)

| Teammate | Role | Deploy When |
|----------|------|-------------|
| 🏗️ **[The Architect](teammates/the-architect.md)** | System design, code review, technical decisions | Building anything new, reviewing PRs |
| 🔍 **[The Researcher](teammates/the-researcher.md)** | Market analysis, competitive intel, feasibility | Evaluating ideas, due diligence |
| ✍️ **[The Writer](teammates/the-writer.md)** | Documentation, content, marketing copy | Docs, READMEs, blog posts, landing pages |
| ⚙️ **[The Operator](teammates/the-operator.md)** | Infrastructure, automation, DevOps | Server setup, CI/CD, cron, debugging |
| 🎯 **[The Strategist](teammates/the-strategist.md)** | Business models, positioning, revenue | Pricing, launch planning, go-to-market |

### Specialist Team (spawn on demand)

| Teammate | Role | Deploy When |
|----------|------|-------------|
| 🔴 **[The Critic](teammates/the-critic.md)** | Adversarial review, red teaming, hole-poking | Before shipping — the "would this actually work?" check |
| 🎨 **[The Designer](teammates/the-designer.md)** | UI/UX, user flows, interface design | Product experience, landing pages |
| 🔭 **[The Scout](teammates/the-scout.md)** | Trend detection, emerging tech, early signals | Weekly recon, finding what's next |

### How Teammates Work

Each teammate file contains:
- **SOUL** — Identity, communication style, operational approach
- **Boundaries** — What they do and don't do (DRA principle)
- **When to Spawn** — Example prompts and situations
- **Quality Standards** — How they verify their own work

### Deploy in Claude Code (Agent Teams)
```
> Spawn a teammate that is an expert architect to review the API design.
> Spawn another teammate that is an expert researcher to find competing products.
> Spawn a third teammate that is an expert critic to stress-test the business model.
```

### Deploy in OpenClaw
```
sessions_spawn(task="[Researcher SOUL context] Research the AI audio plugin market", label="market-research")
```

### Deploy as Persistent Agents
Copy teammate files into dedicated workspaces. Each becomes a persistent specialist with accumulated domain knowledge.

---

## The Identity Files

Every MANGO agent (teammate or otherwise) gets identity files:

| File | Purpose |
|------|---------|
| `SOUL.md` | Core identity — persona, boundaries, tone, values |
| `BOOT.md` | Startup ritual — what to load first |
| `IDENTITY.md` | Name, role, emoji, vibe |
| `TOOLS.md` | Environment-specific notes |
| `MEMORY.md` | Accumulated knowledge |

These files ARE the governance layer. Without them, you have agents. With them, you have a team.

---

## Quick Start

```bash
# Clone
git clone https://github.com/nmsitaras-afk/mango-framework.git
cd mango-framework

# Option 1: Use a teammate directly
# Copy the teammate definition into your agent's system prompt or SOUL.md
cat teammates/the-architect.md

# Option 2: Create a full agent workspace
cp -r templates/starter/ ~/my-first-agent/
# Edit SOUL.md, BOOT.md, IDENTITY.md

# Option 3: Deploy a full team
# See docs/spawning-teammates.md for Claude Code and OpenClaw integration
```

---

## Structure

```
mango-framework/
├── README.md
├── teammates/               ← THE CORE: 8 specialist identities
│   ├── the-architect.md
│   ├── the-researcher.md
│   ├── the-writer.md
│   ├── the-operator.md
│   ├── the-strategist.md
│   ├── the-critic.md
│   ├── the-designer.md
│   └── the-scout.md
├── framework/
│   ├── principles/          # The 6 MANGO principles
│   ├── teammate/            # Identity file templates (SOUL, BOOT, etc.)
│   └── governance/          # Hub-and-spoke swarm patterns
├── templates/
│   ├── starter/             # Minimal: just the 4 identity files
│   └── full/                # Full setup with memory, cron, heartbeat
├── examples/
│   ├── research-team/       # Hub + 3 research specialists
│   ├── dev-team/            # Hub + architect + frontend + backend
│   └── business-ops/        # Hub + analyst + writer + ops
└── docs/
    └── spawning-teammates.md  # Integration guide for Claude Code + OpenClaw
```

---

## Works With

MANGO is framework-agnostic. Use it with:
- **[Claude Code Agent Teams](https://code.claude.com/docs/en/agent-teams)** — Native teammate spawning with `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1`
- **[OpenClaw](https://openclaw.ai)** — Native support for SOUL.md/BOOT.md identity files + sub-agent spawning
- **CrewAI** — Use SOUL.md to define agent backstories
- **AutoGen** — Use SOUL.md as system prompts
- **LangGraph** — Use BOOT.md to define node initialization
- **Any agent framework** — The files are just markdown

---

## Origin Story

Built by Niko Sitaras and his AI teammate Steve while building [Sanctuary](https://sitarasaudio.com) — an AI-powered audio plugin. MANGO emerged from daily practice: coordinating an AI agent that needed to research, write, code, and ship autonomously.

The 8 teammate identities aren't theoretical — they're extracted from real usage patterns. The Researcher is how Steve spawns 6 parallel research sessions. The Architect is how Steve reviews code. The Operator is how Steve manages infrastructure. They work because they've been working.

The framework is named after the fruit because mangoes have one seed at the center (the hub) and everything else grows around it.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) — we welcome new teammates, integration guides, and examples.

## License

MIT — Use it however you want. Build something great.

---

*"The people who are crazy enough to think they can change the world are the ones who do."*
