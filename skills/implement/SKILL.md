---
name: implement
description: Use only after an unknown-first:plan implementation plan is approved, or when the user explicitly overrides the approval gate. Implements against the plan, records deviations in implementation-notes.md, and routes to unknown-first:closeout.
---

# Implement

Read `../references/shared-workflow.md` and use `../references/artifact-templates.md` for implementation notes.

## Inquiry Lens

Ask: "What did reality force us to change from the plan?"

Implementation is the first durable code stage. It should not reopen discovery by default, but it must detect new unknown unknowns that appear in the real codebase and record or escalate them.

## Preconditions

Before implementing, confirm one of:

- The user approved `implementation-plan.md`.
- The task is low risk and approval is unnecessary.
- The user explicitly asked to proceed without approval.

If none is true, stop and route back:

`Blocked: implementation plan needs approval before unknown-first:implement.`

## Procedure

1. Implement against the approved plan.
2. Keep `implementation-notes.md` for medium/high-risk tasks.
3. If an edge case forces a deviation, choose the conservative option unless the risk requires asking.
4. Log deviations under `Deviations` with reason, choice, and follow-up.
5. Run the relevant verification.

## End State

End with:

`Next: use unknown-first:closeout to verify, explain, and prepare memory updates.`
