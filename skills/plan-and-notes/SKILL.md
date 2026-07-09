---
name: plan-and-notes
description: Use after unknown-first:reference when enough decisions are resolved to plan implementation. Creates an approval-gated implementation plan and defines implementation-notes.md deviation tracking before durable code changes.
---

# Plan And Notes

Read `../../references/shared-workflow.md` and use `../../references/artifact-templates.md`.

## Inquiry Lens

Ask: "Which decisions am I most likely to tweak before implementation, and how should deviations be logged if reality forces changes?"

This stage combines the original workflow's implementation plan and implementation notes. It should lead with the reviewable decisions most likely to change, then define how implementation will log edge cases and deviations. It does not implement production changes.

## Procedure

1. Review memory, blindspot notes, brainstorm outputs, prototype notes, interview answers, references, and existing decisions.
2. Create or present `implementation-plan.md`.
3. Lead with decisions the user is most likely to change:
   - Data model
   - Types/interfaces
   - User-facing flow
   - Security/privacy
   - Rollback and migration risk
4. List files to change and why.
5. Include implementation steps, test plan, remaining unknowns, and rollback/risk notes.
6. Define how `implementation-notes.md` will record deviations during implementation.
7. Include an explicit approval gate.

## Rule

Do not implement production changes in this stage.

Do not silently skip this stage before durable implementation. If the task is truly trivial and reversible, propose a lightweight skip, explain why no plan or notes are needed, and ask the user to confirm before implementing.

## End State

End with:

`Approval needed: confirm this plan before using unknown-first:implement.`

Or:

`Proposed skip: unknown-first:plan-and-notes because ...; next would be unknown-first:implement. Confirm before I proceed.`
