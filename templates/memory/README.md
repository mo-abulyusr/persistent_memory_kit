# Memory System

This folder provides persistent coordination memory for agents.

## Layout
- `active/`: latest state for quick loading
- `episodic/`: chronological logs and per-session notes
- `semantic/`: durable facts, project charter, and decisions (ADRs)
- `procedural/`: rules, guardrails, and quality checks
- `archive/`: old or compacted memory

## Canonical project brief
- `memory/semantic/project-charter.md`

## Update cadence
- Read `project-charter`, `active/`, `guardrails`, and decision index at task start.
- Write session notes during work.
- Update active files + progress log + ADRs at task end.
