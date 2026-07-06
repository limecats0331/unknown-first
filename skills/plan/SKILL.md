---
name: plan
description: Use after unknown-first:interview when enough decisions are resolved to plan implementation. Creates an approval-gated implementation-plan.md with high-impact decisions first, then routes to unknown-first:implement only after approval.
---

# Plan

Read `../references/shared-workflow.md` and use `../references/artifact-templates.md`.

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
