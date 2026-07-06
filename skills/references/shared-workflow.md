# Unknown First Shared Workflow

Use these rules across all `unknown-first:*` skills.

## Core Constraint

Do not modify production code during discovery. Before approval, only create analysis notes, disposable prototypes, isolated proofs of concept, or draft artifacts.

Production implementation starts only after:

- Relevant unknowns are classified.
- High-impact decisions are reviewed.
- An implementation plan is approved.

## Memory Files

Prefer this project-local structure:

```text
.unknowns-first/
  project-memory.md
  decisions.md
  resolved-unknowns.md
  open-unknowns.md
  question-log.md
  work/
    YYYY-MM-DD-task-slug/
      blindspot-pass.md
      prototype-notes.md
      interview-answers.md
      implementation-plan.md
      implementation-notes.md
      final-explainer.md
      quiz.md
```

Do not create every file mechanically. Create only what helps the task.

## Re-Ask Policy

Use existing resolved decisions instead of asking again. Re-ask only when:

- The current request conflicts with stored decisions.
- The stored decision's scope is unclear.
- Related requirements or files changed materially.
- The decision affects security, data model, architecture, irreversible migration, or user-visible behavior.

Ask the same project question at most twice. After the second answer, promote it to `resolved-unknowns.md` or `decisions.md` unless the user explicitly keeps it open.

## Unknown Taxonomy

- `Known knowns`: facts already stated in the request, specs, files, or memory.
- `Known unknowns`: questions known to be unresolved.
- `Unknown knowns`: tacit preferences the user may recognize only after seeing examples.
- `Unknown unknowns`: blindspots the user may not know to ask about.

## Stage Order

1. `unknown-first:blindspot-pass`
2. `unknown-first:prototype` when visual/tacit/cheap exploration is useful; otherwise skip to `unknown-first:interview`
3. `unknown-first:interview`
4. `unknown-first:plan`
5. `unknown-first:implement`
6. `unknown-first:closeout`
7. `unknown-first:memory-update`

## Transition Language

End each stage with one of:

- `Next: use unknown-first:<stage> because ...`
- `Skip: unknown-first:<stage> because ...; next use unknown-first:<next-stage>`
- `Blocked: need user answer before continuing`
