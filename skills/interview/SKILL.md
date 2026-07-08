---
name: interview
description: Use after prototype or brainstorm when decisions remain. Asks one question at a time, prioritizing answers that change architecture, data model, UX, security, scope, or implementation cost, then routes to unknown-first:reference.
---

# Interview

Read `../references/shared-workflow.md` and use `../references/artifact-templates.md` if writing files.

## Inquiry Lens

Ask: "Which explicit decisions would change architecture, UX, scope, security, data, or cost?"

Do not skip this just because blindspot-pass, brainstorm, or prototype asked questions. Those stages reveal different unknowns. Interview converts unresolved ambiguity into explicit human decisions, one question at a time.

## Procedure

1. Review memory, blindspot notes, prototype notes, and open unknowns.
2. Build a fresh interview queue from this stage's inquiry lens.
3. Remove only questions already answered in memory or prior artifacts.
4. Ask one question at a time.
5. Prioritize questions whose answer changes architecture, data model, security/privacy, UX flow, scope, cost, or rollback risk.
6. Track asked count in `question-log.md` when project memory exists.
7. Promote answers to `interview-answers.md`, `decisions.md`, or `resolved-unknowns.md` when durable.

## Stop Asking When

- Remaining unknowns are low risk and have handling plans.
- The implementation plan can state assumptions safely.
- The user asks to proceed.

## End State

End with one of:

- `Next: use unknown-first:reference because the blocking decisions are resolved.`
- `Blocked: need answer to [question] before planning.`
