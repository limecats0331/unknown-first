---
name: closeout
description: Compatibility alias for unknown-first:explainer-quiz. Use after implementation to verify the change, produce a final explainer, optionally quiz the user, and route durable learnings to unknown-first:memory-update.
---

# Closeout

Compatibility note: prefer `unknown-first:explainer-quiz` for the canonical workflow name used by the original visual guide. This skill keeps `/unknown-first:closeout` working.

Read `../references/shared-workflow.md` and use `../references/artifact-templates.md` when writing final explainer or quiz files.

## Inquiry Lens

Ask: "Can reviewers understand, approve, and verify what changed, and can the human pass a quiz on it?"

This is not just a summary. It should package the work for buy-in, make hidden behavior, plan deviations, verification evidence, and residual risk visible, and optionally quiz the human so merging is gated on understanding.

## Procedure

1. Summarize what changed and why.
2. Provide verification evidence: tests, screenshots, logs, commands, or manual checks.
3. Explain deviations from the plan.
4. Identify residual risks and follow-ups.
5. If the work was complex, produce a short quiz or checklist to confirm human understanding.
6. Identify decisions and resolved unknowns that should become project memory.

Do not silently skip closeout. For small changes, scale it down to a short verification note. If even that seems unnecessary, propose the skip and ask the user to confirm before memory-update.

## End State

End with:

`Next: use unknown-first:memory-update to promote durable decisions and resolved unknowns.`

Or:

`Proposed skip: unknown-first:closeout because ...; next would be unknown-first:memory-update. Confirm before I proceed.`
