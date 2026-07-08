# Unknown First Artifact Templates

Use these templates when creating durable files.

## blindspot-pass.md

```markdown
# Blindspot Pass: [Task]

## Starting Context

## Relevant Memory

## Known Knowns
- 

## Known Unknowns
- 

## Unknown Knowns To Surface
- 

## Unknown Unknowns / Blindspots
- 

## Files, Sources, Or References To Inspect
- 

## Questions That Could Change The Solution
1. 

## Prototype Decision
Prototype needed: yes | no
Reason:

## Next
Use unknown-first:brainstorm.
```

## prototype-notes.md

```markdown
# Prototype Notes: [Task]

## Prototype Decision
Needed: yes | no
Reason:

## Disposable Scope
- 

## Options Explored
1. 

## User Reactions / Decisions
- 

## Unknowns Resolved
- 

## Remaining Unknowns
- 

## Next
Use unknown-first:interview.
```

## brainstorm-notes.md

```markdown
# Brainstorm Notes: [Task]

## Starting Point

## Candidate Directions
1. 

## Cheap To Ambitious Options
- Cheap:
- Medium:
- Ambitious:

## Unknowns Surfaced
- 

## Prototype Decision
Prototype needed: yes | no
Reason:

## Next
Use unknown-first:prototype | unknown-first:interview.
```

## interview-answers.md

```markdown
# Interview Answers: [Task]

## Questions And Answers

### 1. [Question]
Answer:

Impact:

Promote to memory: yes | no

## Remaining Blockers
- 

## Next
Use unknown-first:plan when no blocking questions remain.
```

## reference-notes.md

```markdown
# Reference Notes: [Task]

## References Used
- 

## Transferable Semantics / Structure / Quality Bar
- 

## Constraints Derived From References
- 

## Decisions Resolved
- 

## Next
Use unknown-first:plan-and-notes.
```

## implementation-plan.md

```markdown
# Implementation Plan: [Task]

## Goal

## Confirmed Decisions
- 

## Resolved Unknowns
- 

## Remaining Unknowns
| Unknown | Risk | Handling |
| --- | --- | --- |

## Decisions To Review First
- Data model:
- Types/interfaces:
- User-facing flow:
- Security/privacy:
- Rollback:

## Files To Change
| File | Reason |
| --- | --- |

## Implementation Steps
1. 

## Test Plan
- 

## Rollback / Risk Notes
- 

## Approval Gate
Implementation starts after user approval.
```

## implementation-notes.md

```markdown
# Implementation Notes: [Task]

## Plan Reference

## Decisions Made During Implementation
- 

## Deviations
| Deviation | Reason | Conservative Choice | Follow-up |
| --- | --- | --- | --- |

## Unknowns Discovered
- 

## Memory Updates To Promote
- 
```

## final-explainer.md

```markdown
# Final Explainer: [Task]

## What Changed
- 

## Why It Changed
- 

## Verification Evidence
- 

## Risks / Follow-ups
- 

## Memory Updates
- 
```

## quiz.md

```markdown
# Verification Quiz: [Task]

1. What behavior changed?
2. Which prior decision constrained the implementation?
3. What deviation, if any, happened during implementation?
4. What evidence proves the change works?
```
