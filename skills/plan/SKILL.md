---
name: plan
description: Compatibility alias for unknown-first:plan-and-notes. Use after unknown-first:reference when enough decisions are resolved to plan implementation. Creates an approval-gated implementation-plan.md with high-impact decisions first, then routes to unknown-first:implement only after approval.
---

# Plan

Compatibility note: prefer `unknown-first:plan-and-notes` for the canonical workflow name used by the original visual guide. This skill keeps `/unknown-first:plan` working.

Read `../references/shared-workflow.md` and use `../references/artifact-templates.md`.

## Inquiry Lens

Ask: "Which decisions am I most likely to tweak before implementation, and how should deviations be logged if reality forces changes?"

Do not merely summarize previous answers. Planning must surface reviewable implementation choices: data model, interfaces, user-facing behavior, security/privacy, migration, rollback, and test strategy. It should also define how implementation notes will record edge cases and deviations.

## Procedure

1. Review memory, blindspot notes, prototype notes, interview answers, and existing decisions.
2. Create or present `implementation-plan.md`.
3. Lead with decisions the user is most likely to change:
   - Data model
   - Types/interfaces
   - User-facing flow
   - Security/privacy
   - Rollback and migration risk
4. List files to change and why.
5. Include implementation steps, test plan, remaining unknowns, and rollback/risk notes.
6. Include an explicit approval gate.

## Rule

Do not implement production changes in this stage.

## End State

End with:

`Approval needed: confirm this plan before using unknown-first:implement.`
