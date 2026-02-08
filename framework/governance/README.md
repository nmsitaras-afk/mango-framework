# MANGO Governance

How to organize a swarm of AI agents that actually gets things done.

## The Problem with Agent Swarms

Most multi-agent frameworks solve plumbing:
- How agents talk to each other
- How tasks get routed
- How memory is shared

Nobody solves management:
- Who decides what to work on?
- How do you prevent agents from duplicating effort?
- How do you maintain quality across a swarm?
- How do you give agents enough autonomy without losing control?

## MANGO's Answer: Governance Architecture

### Hub Agent (The Spoke)
One agent coordinates. It:
- Receives all human requests
- Decomposes tasks and assigns to specialists
- Reviews outputs before delivery
- Maintains the master MEMORY.md
- Says NO to scope creep

### Specialist Agents (The Wheel)
Each specialist owns a domain:
- Has its own SOUL.md (personality, approach)
- Has its own MEMORY.md (domain knowledge)
- Reports to the Hub, not to each other
- Can be spawned on-demand or persistent

### Communication Protocol
- Hub → Specialist: Task assignment with clear scope
- Specialist → Hub: Deliverable + status
- Specialist ↔ Specialist: NEVER direct (prevents chaos)
- All communication logged to files (State-Based Continuity)

## Example: Research Team

```
Hub Agent (Steve)
├── Market Researcher — finds competition, sizing, trends
├── Technical Researcher — feasibility, architecture, stack
├── Writer — produces final docs from research
└── Ops — infrastructure, deployment, monitoring
```

## Example: Dev Team

```
Hub Agent (Steve)  
├── Architect — system design, PRs, code review
├── Frontend — UI, UX, landing pages
├── Backend — APIs, data, infrastructure
└── QA — testing, verification, edge cases
```

## Spawning Teammates in OpenClaw

OpenClaw supports this natively via `agents.list[]` in openclaw.json:

```json
{
  "agents": {
    "list": [
      {
        "id": "researcher",
        "name": "Research Agent",
        "workspace": "~/.openclaw/workspace-researcher",
        "model": "cliproxyapi/claude-sonnet-4-20250514"
      }
    ]
  }
}
```

Or via sub-agents (lighter weight, on-demand):
- `sessions_spawn` creates temporary specialist sessions
- They inherit tools but get isolated context
- Results announce back to the hub

## When to Use Persistent Agents vs Sub-Agents

| | Persistent Agent | Sub-Agent (spawn) |
|---|---|---|
| **Use when** | Ongoing domain, needs memory | One-off task |
| **Memory** | Own MEMORY.md, accumulates knowledge | Temporary, discarded after |
| **Cost** | Higher (always available) | Lower (on-demand) |
| **Setup** | Config change + workspace | One command |
| **Example** | DevOps agent monitoring infra | "Research this topic and email the doc" |
