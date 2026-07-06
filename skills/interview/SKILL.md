---
name: interview
description: Use after blindspot-pass or prototype when decisions remain. Asks one question at a time, prioritizing answers that change architecture, data model, UX, security, scope, or implementation cost, then routes to unknown-first:plan.
---

# Interview

Read `../references/shared-workflow.md` and use `../references/artifact-templates.md` if writing files.

## Procedure

1. Review memory, blindspot notes, prototype notes, and open unknowns.
2. Do not ask questions already answered in memory unless the re-ask policy applies.
3. Ask one question at a time.
4. Prioritize questions whose answer changes architecture, data model, security/privacy, UX flow, scope, cost, or rollback risk.
5. Track asked count in `question-log.md` when project memory exists.
6. Promote answers to `interview-answers.md`, `decisions.md`, or `resolved-unknowns.md` when durable.

## Stop Asking When

- Remaining unknowns are low risk and have handling plans.
- The implementation plan can state assumptions safely.
- The user asks to proceed.

## End State

End with one of:

- `Next: use unknown-first:plan because the blocking decisions are resolved.`
- `Blocked: need answer to [question] before planning.`
