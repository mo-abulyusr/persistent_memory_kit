# ADR-0001: Adopt File-Based Persistent Memory Protocol

- Status: Accepted
- Date: YYYY-MM-DD

## Context
Multiple agents may collaborate over time, but context windows are limited. We need durable, human-readable project memory.

## Decision
Adopt a structured memory folder with:
- `active/` for quick-start state
- `episodic/` for chronological history
- `semantic/` for durable decisions/facts
- `procedural/` for guardrails and quality rules

Require agents to read key memory files at task start and update memory at task end.

## Consequences
### Positive
- Better continuity across agent sessions.
- Easier handoff between agents.
- Durable decision history.

### Negative
- Additional maintenance overhead each task.
- Risk of noisy logs if entries are not curated.
