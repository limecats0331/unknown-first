---
name: memory-update
description: Use after closeout, after repeated questions, or whenever a project unknown becomes a durable known. Updates .unknowns-first project memory so the same question is not repeatedly asked.
---

# Memory Update

Read `../references/shared-workflow.md` and use `../references/artifact-templates.md` for memory formats.

## Procedure

1. Review final explainer, implementation notes, interview answers, and question log.
2. Promote durable facts to `.unknowns-first/project-memory.md`.
3. Promote explicit choices to `.unknowns-first/decisions.md`.
4. Promote formerly open questions to `.unknowns-first/resolved-unknowns.md`.
5. Keep unresolved items in `.unknowns-first/open-unknowns.md`.
6. Update asked counts in `.unknowns-first/question-log.md`.

## Promotion Criteria

Promote an answer when:

- It affects future tasks.
- The user answered it twice.
- It constrains architecture, UX, security, data model, naming, testing, deployment, or workflow.
- Re-asking would waste attention.

## End State

End with a short list of memory updates made and any remaining open unknowns.
