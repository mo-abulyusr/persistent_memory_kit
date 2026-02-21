## Persistent Memory Protocol (Required)

This repository uses file-based memory so multiple agents can coordinate work over time.

### Core Rule
For every task in this repo, follow this protocol unless the user explicitly says to skip memory updates.

### Start of Task
1. Ensure these files exist (create if missing):
- `memory/semantic/project-charter.md`
- `memory/active/current-state.md`
- `memory/active/next-actions.md`
- `memory/active/handoff.md`
- `memory/episodic/progress-log.md`
- `memory/semantic/decisions-index.md`
- `memory/procedural/guardrails.md`
2. Read, at minimum:
- `memory/semantic/project-charter.md`
- `memory/active/current-state.md`
- `memory/active/next-actions.md`
- `memory/procedural/guardrails.md`
- `memory/semantic/decisions-index.md`

### New Session Onboarding
If this is the first assistant turn in a new chat session, do this before making edits:
1. Read the files listed in "Start of Task".
2. Send a short onboarding summary with:
- Overall project goal
- Current state
- Proposed next step
3. Ask the user to confirm priority and wait for a reply.

Exception: If the user's first message explicitly asks for immediate execution, proceed while stating assumptions briefly.

### During Task
1. Keep short session notes in a dated file under `memory/episodic/sessions/YYYY/`.
2. Record only useful facts; avoid noise.

### End of Task
1. Update `memory/active/current-state.md` with the latest state.
2. Update `memory/active/next-actions.md` with concrete next steps.
3. Update `memory/active/handoff.md` with what another agent needs to continue.
4. Append one summary line to `memory/episodic/progress-log.md`.
5. If a durable decision was made, add or update an ADR in `memory/semantic/decisions/` and update `memory/semantic/decisions-index.md`.
6. If new constraints or rules were discovered, update `memory/procedural/guardrails.md`.

### Writing Rules
- Use append-only history for logs and ADRs; do not delete prior entries unless user asks.
- Timestamp entries in ISO-8601 UTC.
- Keep entries concise and factual.
- Never store secrets or private tokens in memory files.
