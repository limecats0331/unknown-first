---
name: blindspot-pass
description: Use before non-trivial work, especially new codebase areas, unfamiliar domains, architecture/data/security/user-facing changes, or when the user asks for a blindspot pass. Identifies unknown unknowns, checks project memory, and routes next to unknown-first:brainstorm.
---

# Blindspot Pass

Read `../references/shared-workflow.md` and use `../references/artifact-templates.md` if writing files.

## Inquiry Lens

Ask: "What has not even been considered yet?"

This stage is not the general requirements interview. It should expose blindspots, risky assumptions, missing context, and unknown unknowns before the workflow decides whether to prototype or interview.

## Procedure

1. Check `.unknowns-first/` memory files if present.
2. State relevant prior decisions briefly.
3. Classify the task risk: `low`, `medium`, `high`, or `exploratory`.
4. Classify ambiguity into known knowns, known unknowns, unknown knowns, and unknown unknowns.
5. Inspect only the context needed to identify blindspots.
6. Produce or update `blindspot-pass.md` for medium/high/exploratory work.
7. Recommend whether brainstorming should be broad or narrow.

## End State

End with exactly one transition:

- `Next: use unknown-first:brainstorm because ...`
- `Skip: unknown-first:brainstorm because the task is already fully scoped; next use unknown-first:interview`
- `Blocked: need user answer before continuing`
