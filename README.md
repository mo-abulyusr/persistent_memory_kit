# Persistent Memory Kit

A clean, reusable memory system for project work that spans many sessions, many decisions, and many handoffs.

---

## Why this exists

When work continues across days, tools, and contributors, context gets lost.

This kit keeps important context in files, not in short-term chat history. It gives every new session a stable starting point:
- What this project is trying to achieve
- Where things stand right now
- What was decided and why
- What should happen next

---

## What you get

- A ready-to-copy `memory/` folder structure
- A reusable `AGENTS.md` protocol for consistent behavior
- Starter templates for goals, progress, decisions, handoff, and guardrails

Everything is plain Markdown. Easy to read, easy to version, easy to audit.

---

## Core idea

Use four memory layers, each with a different job:

| Layer | Purpose | Typical files |
|---|---|---|
| **Active** | Current working state | `current-state.md`, `next-actions.md`, `handoff.md` |
| **Episodic** | Time-ordered history | `progress-log.md`, dated session notes |
| **Semantic** | Durable knowledge and decisions | `project-charter.md`, ADRs, facts |
| **Procedural** | Operating rules | `guardrails.md`, runbooks, quality gates |

This separation keeps memory clean. Fast-moving notes do not pollute durable decisions.

---

## Folder layout

```text
templates/
  AGENTS.md
  memory/
    README.md
    active/
      current-state.md
      next-actions.md
      handoff.md
    episodic/
      progress-log.md
      sessions/
    semantic/
      project-charter.md
      decisions-index.md
      decisions/
        ADR-0001-persistent-memory-protocol.md
      facts.md
      glossary.md
    procedural/
      guardrails.md
      runbooks.md
      quality-gates.md
    archive/
```

---

## Quick start

From the root of your target project:

```bash
git clone https://github.com/mo-abulyusr/persistent_memory_kit.git /tmp/persistent_memory_kit \
  && rsync -av /tmp/persistent_memory_kit/templates/ ./ \
  && rm -rf /tmp/persistent_memory_kit
```

That command copies the template `memory/` structure and `AGENTS.md` into your project.

---

## First-time setup (2 minutes)

1. Open `memory/semantic/project-charter.md`.
2. Fill mission, goals, non-goals, success criteria, constraints.
3. Save.

That file becomes the canonical project brief for every future session.

---

## How daily workflow works

At task start:
1. Read project charter, current state, next actions, guardrails, and decision index.

During work:
1. Keep short session notes in `memory/episodic/sessions/`.

At task end:
1. Update active memory files.
2. Append one line in `progress-log.md`.
3. Add an ADR for any durable decision.
4. Update guardrails if new constraints are discovered.

---

## File guide

- `AGENTS.md`
Defines the memory protocol to follow on each task.

- `memory/semantic/project-charter.md`
The north star: purpose, goals, strategy, constraints.

- `memory/active/current-state.md`
Snapshot of what is true right now.

- `memory/active/next-actions.md`
The immediate action queue.

- `memory/active/handoff.md`
What the next contributor needs to continue smoothly.

- `memory/episodic/progress-log.md`
One-line timeline of meaningful progress.

- `memory/semantic/decisions/*.md`
Decision records (ADRs): what was chosen, why, and tradeoffs.

- `memory/procedural/guardrails.md`
Behavior constraints and working standards.

---

## Customization tips

- Keep paths relative in `AGENTS.md` for portability.
- Keep logs concise; avoid noisy updates.
- Use ADRs only for durable decisions.
- Keep `current-state.md` short enough to scan quickly.

---

## Suggested adaptation for different tools

If your environment uses a different instruction filename, keep the same protocol and adapt the filename accordingly.

---

## Philosophy

Memory should be:
- **Durable** enough to survive session boundaries
- **Structured** enough to be scanned quickly
- **Simple** enough to maintain daily

This kit is designed to stay useful when projects get messy.
