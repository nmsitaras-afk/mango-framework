# Spawning Teammates — Practical Guide

## Method 1: Sub-Agents (Lightweight, On-Demand)

Best for: one-off tasks, research, document creation, parallel work.

In OpenClaw, use `sessions_spawn`:

```
Task: "Research the competitive landscape for AI-powered audio tools"
Label: "market-research"
Model: "sonnet" (cheaper for research) or "opus" (for deep analysis)
```

The sub-agent:
- Gets its own isolated session
- Can use all tools (web search, file read/write, exec)
- Announces results back to the hub when done
- Session can be kept or deleted after

**This is what Steve uses today** — the 6 parallel research docs were all sub-agents.

## Method 2: Persistent Agents (Full Teammates)

Best for: ongoing domains, agents that need to build knowledge over time.

### Step 1: Create the workspace
```bash
mkdir -p ~/.openclaw/workspace-researcher
```

### Step 2: Write the identity files
Copy from `mango-framework/framework/teammate/` templates:
```bash
cp mango-framework/framework/teammate/*.md ~/.openclaw/workspace-researcher/
```

Edit each file:
- **SOUL.md** — Define personality, approach, boundaries
- **BOOT.md** — Define startup ritual, priority stack
- **IDENTITY.md** — Name, role, vibe
- **TOOLS.md** — Environment-specific notes

### Step 3: Add to openclaw.json
```json
{
  "agents": {
    "list": [
      {
        "id": "researcher",
        "name": "Research Specialist",
        "workspace": "~/.openclaw/workspace-researcher",
        "model": { "primary": "cliproxyapi/claude-sonnet-4-20250514" }
      }
    ]
  },
  "bindings": [
    {
      "agentId": "researcher",
      "match": {
        "channel": "telegram",
        "peer": { "kind": "dm", "id": "TELEGRAM_USER_ID" }
      }
    }
  ]
}
```

### Step 4: Restart gateway
```bash
openclaw gateway restart
```

## Method 3: Hybrid (Hub + Specialists)

The MANGO way:
1. **Hub agent** (Steve) handles all human communication
2. Hub **spawns sub-agents** for parallel tasks
3. Critical domains get **persistent agents** that accumulate knowledge
4. Hub reviews all outputs before delivery (Demo Culture)

## Naming Convention

Use the MANGO naming pattern:
- `hub-steve` — Main coordinator
- `spec-researcher` — Research specialist  
- `spec-devops` — Infrastructure/ops specialist
- `spec-writer` — Content/docs specialist
- `temp-*` — Temporary sub-agents (auto-cleaned)

## The Golden Rule

> "Orchestration tells agents how to talk.  
> Governance tells agents what to focus on."  
> — MANGO Framework

The teammate files (SOUL.md, BOOT.md) ARE the governance layer.
Without them, you have agents. With them, you have a team.
