---
name: blindspot-pass
description: Use before non-trivial work, especially new codebase areas, unfamiliar domains, architecture/data/security/user-facing changes, or when the user asks for a blindspot pass. Identifies unknown unknowns, checks project memory, and routes next to unknown-first:prototype or unknown-first:interview.
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
7. Decide whether `unknown-first:prototype` is useful.

## Prototype Routing

Route to `unknown-first:prototype` when:

- The task has UI, UX, visual, document, report, workflow, or interaction taste.
- The user may only know the right answer after seeing options.
- Several implementation approaches are plausible and cheap to mock.
- A disposable HTML/mock/fake-data artifact can prevent expensive rework.

Skip prototype and route to `unknown-first:interview` when:

- Criteria are already explicit.
- Work is backend/internal and follows an existing pattern.
- A prototype would cost more than answering questions.
- Uncertainty is mainly policy, architecture, security, or scope.

## End State

End with exactly one transition:

- `Next: use unknown-first:prototype because ...`
- `Skip: unknown-first:prototype because ...; next use unknown-first:interview`
- `Blocked: need user answer before continuing`
