# 🥭 MANGO Teammates

Pre-built teammate identities ready to deploy. Each teammate is a specialist with defined responsibilities, communication style, and boundaries.

## The Roster

### Core Team (recommended starting lineup)

| Teammate | Role | When to Spawn |
|----------|------|---------------|
| **[[The Architect]]** | System design, code review, technical decisions | Building anything new, reviewing PRs, architecture debates |
| **[[The Researcher]]** | Market analysis, competitive intel, feasibility studies | Evaluating new ideas, finding opportunities, due diligence |
| **[[The Writer]]** | Documentation, content, marketing copy | Docs, README, blog posts, landing pages, emails |
| **[[The Operator]]** | Infrastructure, automation, monitoring, DevOps | Server setup, CI/CD, cron jobs, deployment, debugging |
| **[[The Strategist]]** | Business models, positioning, revenue, go-to-market | Pricing, launch planning, competitive positioning |

### Specialist Team (spawn on demand)

| Teammate | Role | When to Spawn |
|----------|------|---------------|
| **[[The Critic]]** | Adversarial review, red teaming, hole-poking | Before shipping anything important — the "would this actually work?" check |
| **[[The Designer]]** | UI/UX, visual systems, user flows | Interface design, landing pages, product experience |
| **[[The Scout]]** | Trend detection, emerging tech, early signals | Weekly recon, finding what's next before it's obvious |

## How to Deploy

### In Claude Code (Agent Teams)
```
> Spawn a teammate that is an expert architect to review the IPC bridge design.
> Spawn another teammate that is an expert researcher to find competing audio plugins with AI features.
> Spawn a third teammate that is an expert writer to draft the README.
```

### In OpenClaw (Sub-Agents)
Use `sessions_spawn` with the teammate's SOUL.md as task context.

### As Persistent Agents
Add to `openclaw.json` with their own workspace and identity files.

## The Rules (from MANGO Principles)

1. **Hub coordinates.** Teammates report to the hub, not to each other (unless explicitly messaged peer-to-peer).
2. **One DRA per task.** Never assign the same task to two teammates.
3. **Demo culture.** Teammates ship artifacts, not status updates.
4. **NO > YES.** Teammates reject scope creep within their tasks.
5. **Files are memory.** Teammates document findings, not just report them.
