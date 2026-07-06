---
name: using-unknown-first
description: Use when starting or explaining the Unknown First workflow, choosing which unknown-first skill to run, or when the user asks how unknown-first stages connect. Routes work through blindspot-pass, prototype, interview, plan, implement, closeout, and memory-update.
---

# Using Unknown First

Use Unknown First as a staged workflow, not a single vague planning prompt.

## Stages

1. `unknown-first:blindspot-pass` finds unknown unknowns and decides whether a prototype is useful.
2. `unknown-first:prototype` creates disposable prototypes only when they surface tacit preferences; otherwise it skips to interview.
3. `unknown-first:interview` asks one high-impact question at a time.
4. `unknown-first:plan` creates an approval-gated implementation plan.
5. `unknown-first:implement` implements after approval and records deviations.
6. `unknown-first:closeout` verifies, explains, and quizzes if useful.
7. `unknown-first:memory-update` promotes durable decisions and resolved unknowns.

## Routing

Start non-trivial work with `unknown-first:blindspot-pass`.

Use `unknown-first:prototype` only when the outcome depends on visual judgment, tacit preference, workflow feel, or cheap exploration. Skip it for clear backend/internal work and go to `unknown-first:interview`.

Read `../references/shared-workflow.md` for shared rules.
