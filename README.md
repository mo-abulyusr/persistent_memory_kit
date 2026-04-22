# Memory Bank

Memory Bank is a persistent-memory protocol for coding agents. It gives every new session a durable place to find project context, current focus, decisions, and progress so work survives across sessions, handoffs, and long pauses.

## Why It Exists

Agent sessions reset. Projects do not.

Memory Bank exists so the next agent can answer, quickly and consistently:
- What is this project?
- What matters right now?
- What has already been decided?
- What changed recently?
- What should happen next?

The goal is not "take more notes." The goal is to make ongoing work survivable across resets, handoffs, and long gaps.

## What You Install

This repo ships one installable template set:

```text
templates/
  AGENTS.md
  memory-bank/
    projectbrief.md
    activecontext.md
    decisionlog.md
    progress.md
```

`templates/AGENTS.md` is the full operational rule, not a summary. It tells the agent how to bootstrap Memory Bank, what to read first, when to update memory, and how to compact it as the project evolves.

The four memory files have distinct roles:
- `projectbrief.md` - stable project purpose, structure, constraints, conventions
- `activecontext.md` - current focus, blockers, and next steps, organized by workstream
- `decisionlog.md` - durable decisions and rationale
- `progress.md` - completed work, in-progress work, known issues

## Protocol At A Glance

1. Start every session by checking for `memory-bank/`.
2. If it does not exist, bootstrap it from the provided templates.
3. Always read `projectbrief.md` and `activecontext.md` before doing work.
4. Read `decisionlog.md` and `progress.md` whenever the task touches decisions, planning, or recent status.
5. Update the relevant memory files silently after meaningful progress.
6. Compact the files when they exceed the rule's size budgets.

This keeps the system useful instead of turning it into a forgotten notes folder.

## How To Use It

Copy the template files into the target project root:

```bash
git clone https://github.com/mo-abulyusr/memory-bank.git /tmp/memory-bank \
  && rsync -a /tmp/memory-bank/templates/ ./ \
  && rm -rf /tmp/memory-bank
```

That gives the project:
- a root `AGENTS.md` with the full Memory Bank protocol
- a `memory-bank/` folder with the four durable context files

Then:
1. Fill in `memory-bank/projectbrief.md` with real project facts.
2. Let agents keep `activecontext.md`, `decisionlog.md`, and `progress.md` current as work changes.
3. Keep the folder in the project root so future sessions can pick up where the last one left off.

## What Makes This Different

Memory Bank is opinionated on purpose:
- agents read context before they act
- agents update memory continuously, not just at the end
- `activecontext.md` is multi-agent aware
- structure maps must be specific enough that an agent can find code without re-scanning the repo
- the system includes compaction rules so the files stay useful as they grow

That is the difference between "some markdown notes" and a durable working memory.

## Source Of Truth

This repo keeps two forms of the rule:
- `memory-bank-full-rule/memory-bank.mdc` - source/reference copy of the full rule
- `templates/AGENTS.md` - installable AGENTS-friendly version of that same rule
- `templates/memory-bank/*.md` - bootstrap templates expected by the rule

If you update the rule, keep those surfaces aligned.

## Writing Rules

Memory Bank entries should stay:
- telegraphic
- factual
- one fact per line
- path-first instead of code-heavy
- free of secrets

If a note does not help the next session move faster, it probably does not belong in Memory Bank.
