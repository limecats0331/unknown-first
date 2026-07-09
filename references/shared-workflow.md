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
      brainstorm-notes.md
      prototype-notes.md
      interview-answers.md
      reference-notes.md
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

## Stage Independence

Stages are ordered, but they are not a single question list split into parts. Each stage must run its own distinct inquiry lens:

- `blindspot-pass` asks: "What questions, quality bars, history, and potholes am I not aware enough to ask about?"
- `brainstorm` asks: "What possible approaches might be valuable before we narrow the scope?"
- `prototype` asks: "What tacit preference or quality bar only becomes clear when seen?"
- `interview` asks: "Which explicit decisions would change architecture, UX, scope, security, data, or cost?"
- `reference` asks: "What reference can communicate the desired behavior better than prose?"
- `plan-and-notes` asks: "Which decisions am I most likely to tweak before implementation, and how should deviations be logged if reality forces changes?"
- `implement` asks: "What did reality force us to change from the plan?"
- `explainer-quiz` asks: "Can reviewers understand, approve, and verify what changed, and can the human pass a quiz on it?"
- `memory-update` asks: "What should never need to be re-asked in this project?"

Do not skip a stage's own checks merely because a previous stage asked questions. Use previous artifacts as inputs, then ask what this stage uniquely reveals. Skip a stage only when its inquiry lens is not useful for the current task, and state why.

## Stage Order

1. `unknown-first:blindspot-pass`
2. `unknown-first:brainstorm`
3. `unknown-first:prototype` when visual/tacit/cheap exploration is useful; otherwise skip to `unknown-first:interview`
4. `unknown-first:interview`
5. `unknown-first:reference`
6. `unknown-first:plan-and-notes`
7. `unknown-first:implement`
8. `unknown-first:explainer-quiz`
9. `unknown-first:memory-update`

## Skipping Policy

Treat `prototype` as the main optional discovery stage. Skip it when the task is pure logic/backend/internal work, follows an existing pattern, or when a mock would not reduce uncertainty.

For the other stages, do at least a lightweight pass unless the task is truly trivial and reversible. A lightweight pass may be one or two sentences, but it must explicitly apply the stage's inquiry lens.

Do not silently skip any stage. When a stage appears unnecessary, state the skip reason, name the next stage, and ask the user to confirm before proceeding. Proceed without asking only when the user has already explicitly authorized automatic skip decisions for the current run.

- Do not skip `blindspot-pass` for non-trivial work.
- Do not skip `brainstorm` unless the task is already fully scoped.
- Do not skip `interview` while decisions remain.
- Do not skip `reference`; if no reference is needed, say so before planning.
- Do not skip `plan-and-notes` before durable implementation.
- Do not skip `implement` when production changes are needed.
- Do not skip `explainer-quiz`; scale it down for small changes.
- Do not skip `memory-update`; say "no durable memory updates" when nothing should be promoted.

## Transition Language

End each stage with one of:

- `Next: use unknown-first:<stage> because ...`
- `Proposed skip: unknown-first:<stage> because ...; next would be unknown-first:<next-stage>. Confirm before I proceed.`
- `Blocked: need user answer before continuing`
