---
name: using-unknown-first
description: Use when starting or explaining the Unknown First workflow, choosing which unknown-first skill to run, or when the user asks how unknown-first stages connect. Routes work through blindspot-pass, brainstorm, prototype, interview, reference, plan-and-notes, implement, explainer-quiz, and memory-update.
---

# Using Unknown First

Use Unknown First as a staged workflow, not a single vague planning prompt.

## Stages

Each stage has its own inquiry lens. Do not treat later stages as merely continuing the previous stage's questions.

1. `unknown-first:blindspot-pass` asks what questions, quality bars, history, and potholes the human is not aware enough to ask about.
2. `unknown-first:brainstorm` asks what possible approaches might be valuable before narrowing scope.
3. `unknown-first:prototype` asks what tacit preference or quality bar only becomes clear when seen.
4. `unknown-first:interview` asks which explicit decisions would change architecture, UX, scope, security, data, or cost.
5. `unknown-first:reference` asks what reference can communicate the desired behavior better than prose.
6. `unknown-first:plan-and-notes` asks which decisions the human is most likely to tweak before implementation and how deviations should be logged if reality forces changes.
7. `unknown-first:implement` asks what reality forced us to change from the plan.
8. `unknown-first:explainer-quiz` asks whether reviewers can understand, approve, and verify what changed, and whether the human can pass a quiz on it.
9. `unknown-first:memory-update` asks what should never need to be re-asked in this project.

## Routing

Start non-trivial work with `unknown-first:blindspot-pass`, then use `unknown-first:brainstorm` unless the task is already fully scoped.

Use `unknown-first:prototype` only when the outcome depends on visual judgment, tacit preference, workflow feel, or cheap exploration. Skip it for clear backend/internal work and go to `unknown-first:interview`.

Read `../references/shared-workflow.md` for shared rules.
