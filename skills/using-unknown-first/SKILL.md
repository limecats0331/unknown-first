---
name: using-unknown-first
description: Use when starting or explaining the Unknown First workflow, choosing which unknown-first skill to run, or when the user asks how unknown-first stages connect. Routes work through blindspot-pass, prototype, interview, plan, implement, closeout, and memory-update.
---

# Using Unknown First

Use Unknown First as a staged workflow, not a single vague planning prompt.

## Stages

Each stage has its own inquiry lens. Do not treat later stages as merely continuing the previous stage's questions.

1. `unknown-first:blindspot-pass` asks what has not even been considered yet.
2. `unknown-first:prototype` asks what tacit preference or quality bar only becomes clear when seen.
3. `unknown-first:interview` asks which explicit decisions would change architecture, UX, scope, security, data, or cost.
4. `unknown-first:plan` asks which implementation choices need review before code changes.
5. `unknown-first:implement` asks what reality forced us to change from the plan.
6. `unknown-first:closeout` asks whether the human can understand and verify what changed.
7. `unknown-first:memory-update` asks what should never need to be re-asked in this project.

## Routing

Start non-trivial work with `unknown-first:blindspot-pass`.

Use `unknown-first:prototype` only when the outcome depends on visual judgment, tacit preference, workflow feel, or cheap exploration. Skip it for clear backend/internal work and go to `unknown-first:interview`.

Read `../references/shared-workflow.md` for shared rules.
