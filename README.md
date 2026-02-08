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

## The Teammate System

MANGO includes a complete identity architecture for AI agents. Each agent gets:

| File | Purpose |
|------|---------|
| `SOUL.md` | Core identity — persona, boundaries, tone |
| `BOOT.md` | Startup ritual — what to load first |
| `IDENTITY.md` | Name, role, vibe |
| `TOOLS.md` | Environment-specific notes |
| `MEMORY.md` | Accumulated knowledge |

These files ARE the governance layer. Without them, you have agents. With them, you have a team.

## Quick Start

```bash
# Clone
git clone https://github.com/nmsitaras-afk/mango-framework.git
cd mango-framework

# Copy a starter template for your first agent
cp -r templates/starter/ ~/my-first-teammate/

# Edit the identity files
edit ~/my-first-teammate/SOUL.md
edit ~/my-first-teammate/BOOT.md
edit ~/my-first-teammate/IDENTITY.md
```

## Works With

MANGO is framework-agnostic. Use it with:
- **OpenClaw** — Native support for SOUL.md/BOOT.md identity files
- **CrewAI** — Use SOUL.md to define agent backstories
- **AutoGen** — Use SOUL.md as system prompts
- **LangGraph** — Use BOOT.md to define node initialization
- **Any agent framework** — The files are just markdown

## Structure

```
mango-framework/
├── README.md
├── framework/
│   ├── principles/          # The 6 MANGO principles
│   ├── teammate/            # Identity file templates
│   └── governance/          # Swarm organization patterns
├── templates/
│   ├── starter/             # Minimal: just the 4 identity files
│   └── full/                # Full setup with memory, cron, scripts
├── examples/
│   ├── research-team/       # Hub + 3 research specialists
│   ├── dev-team/            # Hub + architect + frontend + backend
│   └── business-ops/        # Hub + analyst + writer + ops
└── docs/
    └── spawning-teammates.md
```

## Origin Story

Built by Niko Sitaras and his AI teammate Steve while building [Sanctuary](https://sitarasaudio.com) — an AI-powered audio plugin. MANGO emerged from the daily practice of coordinating an AI agent that needed to research, write, code, and ship autonomously.

The framework is named after the fruit because mangoes have one seed at the center (the hub) and everything else grows around it.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) — we welcome examples, integrations, and principle refinements.

## License

MIT — Use it however you want. Build something great.

---

*"The people who are crazy enough to think they can change the world are the ones who do."*
