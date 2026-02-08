# HEARTBEAT

## Checks (rotate, don't run all every time)
- [ ] Time sync: compare system time vs session time
- [ ] Pending tasks from priority stack
- [ ] System health (disk, processes)
- [ ] Memory: been 3+ days since consolidation? Run maintenance

## Rules
- Only escalate if: deadline approaching, something broken, or someone waiting
- If unsure whether to notify: don't. Log it.
- Reply HEARTBEAT_OK if nothing needs attention.
