# Unknown First

Unknown First is a Claude Code / Codex workflow plugin for resolving project unknowns before durable implementation.

Korean README: [README.ko.md](README.ko.md)

## Why This Exists

This plugin is based on a simple working lesson: for strong agentic models, output quality is often bottlenecked less by raw model capability and more by how well the human clarifies the unknowns the model would otherwise have to guess through.

The core framing comes from "the map is not the territory":

- The **map** is the prompt, context, skills, specs, and references given to the agent.
- The **territory** is the actual codebase, domain, users, constraints, and team preferences.
- **Unknowns** are the gaps between the map and the territory.

Unknown First turns that idea into a reusable workflow. It asks the agent to surface blindspots, use disposable prototypes only when they reduce uncertainty, interview the human for high-impact decisions, write an approval-gated plan, record deviations during implementation, and promote resolved unknowns into project memory so the same questions are not asked repeatedly.

Source inspiration:

- [A Field Guide to Fable: Finding Your Unknowns](https://x.com/trq212/article/2073100352921215386) by Thariq
- [Superpowers](https://github.com/obra/superpowers), especially its namespaced skill workflow style

## Workflow

It turns "just implement this" into a staged process:

1. `unknown-first:blindspot-pass`
2. `unknown-first:prototype`
3. `unknown-first:interview`
4. `unknown-first:plan`
5. `unknown-first:implement`
6. `unknown-first:closeout`
7. `unknown-first:memory-update`

The workflow keeps production code untouched during discovery. Disposable prototypes, notes, isolated proofs of concept, and draft artifacts are allowed before approval.

Each stage has a distinct inquiry lens. Later stages should not assume earlier questions covered their job:

- `blindspot-pass`: what has not even been considered yet?
- `prototype`: what tacit preference only becomes clear when seen?
- `interview`: which explicit decisions would change architecture, UX, scope, security, data, or cost?
- `plan`: which implementation choices need review before code changes?
- `implement`: what did reality force us to change from the plan?
- `closeout`: can the human understand and verify what changed?
- `memory-update`: what should never need to be re-asked?

## Commands

Use the plugin with namespaced skills:

```text
/unknown-first:blindspot-pass
/unknown-first:prototype
/unknown-first:interview
/unknown-first:plan
/unknown-first:implement
/unknown-first:closeout
/unknown-first:memory-update
```

`prototype` is optional. It explicitly skips to `interview` when a mock or disposable artifact would not reduce uncertainty.

## Claude Code

Run directly from this directory:

```bash
claude --plugin-dir /path/to/unknown-first
```

For a permanent local install, add a Claude marketplace whose entry points to this plugin directory. During local development this repository was installed from a parent marketplace like:

```bash
claude plugin marketplace add /path/to/local-marketplace-root
claude plugin install unknown-first@unknown-first-local
```

## Codex

The Codex manifest is in `.codex-plugin/plugin.json`.

For local personal marketplace use, add an entry that points to this plugin directory. A personal marketplace entry should point at the plugin root with:

```text
./plugins/unknown-first
```

## Project Memory

The workflow writes durable project learnings under:

```text
.unknowns-first/
  project-memory.md
  decisions.md
  resolved-unknowns.md
  open-unknowns.md
  question-log.md
```

Those files are project runtime memory and are ignored by this plugin repository.

## Source Layout

```text
.claude-plugin/plugin.json
.codex-plugin/plugin.json
skills/
  blindspot-pass/
  prototype/
  interview/
  plan/
  implement/
  closeout/
  memory-update/
  using-unknown-first/
  references/
```

## Validation

Claude:

```bash
claude plugin validate .
```

Codex:

```bash
python3 /path/to/plugin-creator/scripts/validate_plugin.py .
```
