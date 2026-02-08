# Example: Research Team

A hub agent coordinating three specialists to produce research documents.

## Architecture

```
Hub (coordinator)
├── Market Researcher — competition, sizing, trends, pricing
├── Tech Researcher — feasibility, architecture, stack decisions  
└── Writer — synthesizes research into polished deliverables
```

## How It Works

1. Human asks Hub: "Research the plugin flash sales bot market"
2. Hub decomposes into sub-tasks
3. Hub spawns Market Researcher: "Find all competitors, pricing, market size"
4. Hub spawns Tech Researcher: "Evaluate MVP architecture, costs, timeline"
5. Both deliver findings back to Hub
6. Hub spawns Writer: "Synthesize these findings into a strategy doc"
7. Hub reviews, emails, notifies human

## OpenClaw Config

```json
{
  "agents": {
    "list": [
      { "id": "hub", "workspace": "~/.openclaw/workspace-hub" },
      { "id": "market", "workspace": "~/.openclaw/workspace-market", "model": "sonnet" },
      { "id": "tech", "workspace": "~/.openclaw/workspace-tech", "model": "sonnet" },
      { "id": "writer", "workspace": "~/.openclaw/workspace-writer", "model": "opus" }
    ]
  }
}
```

Or use sub-agents (lighter weight):
The Hub uses `sessions_spawn` to create temporary specialists on demand.
This is the recommended approach until you need persistent domain knowledge.
