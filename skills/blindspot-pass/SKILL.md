---
name: blindspot-pass
description: Use before non-trivial work, especially new codebase areas, unfamiliar domains, architecture/data/security/user-facing changes, or when the user asks for a blindspot pass. Identifies unknown unknowns, checks project memory, and routes next to unknown-first:brainstorm.
---

# Blindspot Pass

Read `../../references/shared-workflow.md` and use `../../references/artifact-templates.md` if writing files.

## Inquiry Lens

Ask: "What questions, quality bars, history, and potholes am I not aware enough to ask about?"

This stage is not the general requirements interview. It should expose blindspots, risky assumptions, missing context, unknown unknowns, historical work, hidden traps, and what "good" might look like before the workflow decides whether to brainstorm, prototype, or interview.

## Procedure

1. Check `.unknowns-first/` memory files if present.
2. State relevant prior decisions briefly.
3. Classify the task risk: `low`, `medium`, `high`, or `exploratory`.
4. Classify ambiguity into known knowns, known unknowns, unknown knowns, and unknown unknowns.
5. Inspect only the context needed to identify blindspots.
6. Produce or update `blindspot-pass.md` for medium/high/exploratory work.
7. Recommend whether brainstorming should be broad or narrow.

## End State

Do not silently skip brainstorm. If the task appears fully scoped, propose the skip, explain why, and ask the user to confirm before proceeding to interview.

End with exactly one transition:

- `Next: use unknown-first:brainstorm because ...`
- `Proposed skip: unknown-first:brainstorm because the task is already fully scoped; next would be unknown-first:interview. Confirm before I proceed.`
- `Blocked: need user answer before continuing`
