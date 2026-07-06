# Unknown First

Unknown First is a Claude Code / Codex workflow plugin for resolving project unknowns before durable implementation.

It turns "just implement this" into a staged process:

1. `unknown-first:blindspot-pass`
2. `unknown-first:prototype`
3. `unknown-first:interview`
4. `unknown-first:plan`
5. `unknown-first:implement`
6. `unknown-first:closeout`
7. `unknown-first:memory-update`

The workflow keeps production code untouched during discovery. Disposable prototypes, notes, isolated proofs of concept, and draft artifacts are allowed before approval.

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
