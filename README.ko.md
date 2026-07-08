# Unknown First

Unknown First는 실제 구현에 들어가기 전에 프로젝트의 unknown을 찾아 줄이고, 결정된 내용을 프로젝트 메모리로 남기기 위한 Claude Code / Codex workflow plugin입니다.

English README: [README.md](README.md)

## 왜 만들었나

이 plugin은 강한 agentic model을 쓸수록 결과 품질의 병목이 모델 성능 자체보다, 사람이 모델이 추측해야 할 unknown을 얼마나 잘 드러내고 줄이느냐로 옮겨간다는 문제의식에서 출발했습니다.

핵심 프레임은 "지도는 영토가 아니다"입니다.

- **지도**는 agent에게 주는 prompt, context, skill, spec, reference입니다.
- **영토**는 실제 codebase, domain, user, constraint, team preference입니다.
- **Unknown**은 지도와 영토 사이의 빈칸입니다.

Unknown First는 이 아이디어를 재사용 가능한 절차로 바꿉니다. Agent가 먼저 blindspot을 찾고, 필요한 경우에만 disposable prototype으로 암묵적 판단 기준을 끌어내며, 중요한 결정은 interview로 확인하고, 승인 가능한 implementation plan을 만든 뒤, 구현 중 deviation을 기록하고, resolved unknown을 project memory로 승격해 같은 질문을 반복하지 않게 합니다.

출처/영감:

- Thariq의 [A Field Guide to Fable: Finding Your Unknowns](https://x.com/trq212/article/2073100352921215386)
- [Superpowers](https://github.com/obra/superpowers), 특히 namespaced skill workflow 방식

## Workflow

Unknown First는 "그냥 구현해줘"를 다음 단계형 프로세스로 바꿉니다.

1. `unknown-first:blindspot-pass`
2. `unknown-first:brainstorm`
3. `unknown-first:prototype`
4. `unknown-first:interview`
5. `unknown-first:reference`
6. `unknown-first:plan-and-notes`
7. `unknown-first:implement`
8. `unknown-first:explainer-quiz`
9. `unknown-first:memory-update`

Discovery 단계에서는 production code를 수정하지 않습니다. 승인 전에는 disposable prototype, note, isolated proof of concept, draft artifact만 허용합니다.

각 단계는 서로 다른 질문 렌즈를 가집니다. 뒤 단계가 앞 단계의 질문을 이어받는다고 가정하면 안 됩니다.

- `blindspot-pass`: 아직 고려조차 하지 못한 것은 무엇인가?
- `brainstorm`: 범위를 좁히기 전에 어떤 접근 가능성이 있는가?
- `prototype`: 실제로 봐야 드러나는 암묵적 기준은 무엇인가?
- `interview`: architecture, UX, scope, security, data, cost를 바꿀 명시적 결정은 무엇인가?
- `reference`: 말보다 더 정확하게 원하는 동작을 전달할 reference는 무엇인가?
- `plan-and-notes`: 코드 변경 전에 검토해야 할 구현 선택은 무엇이고, 현실이 계획을 바꾸게 만들 때 무엇을 기록해야 하는가?
- `implement`: 실제 코드베이스가 계획에서 바꾸게 만든 것은 무엇인가?
- `explainer-quiz`: 사람이 변경 내용을 이해하고 검증할 수 있는가?
- `memory-update`: 앞으로 같은 프로젝트에서 다시 묻지 않아야 할 것은 무엇인가?

## Commands

Plugin은 namespaced skill 형태로 사용합니다.

```text
/unknown-first:blindspot-pass
/unknown-first:brainstorm
/unknown-first:prototype
/unknown-first:interview
/unknown-first:reference
/unknown-first:plan-and-notes
/unknown-first:implement
/unknown-first:explainer-quiz
/unknown-first:memory-update
```

`prototype`은 항상 필요한 단계가 아닙니다. Mock이나 disposable artifact가 불확실성을 줄이지 못하는 경우에는 명시적으로 `interview`로 넘어갑니다.

이전 사용법과의 호환을 위해 `/unknown-first:plan`은 `plan-and-notes` 단계의 alias로, `/unknown-first:closeout`은 `explainer-quiz` 단계의 alias로 남겨두었습니다.

## Claude Code

이 디렉토리에서 바로 실행할 수 있습니다.

```bash
claude --plugin-dir /path/to/unknown-first
```

영구적인 local install을 원하면, 이 plugin directory를 가리키는 Claude marketplace를 추가한 뒤 설치합니다.

```bash
claude plugin marketplace add /path/to/local-marketplace-root
claude plugin install unknown-first@unknown-first-local
```

## Codex

Codex manifest는 `.codex-plugin/plugin.json`에 있습니다.

Local personal marketplace를 사용할 경우, marketplace entry가 plugin root를 가리키도록 설정합니다.

```text
./plugins/unknown-first
```

## Project Memory

Workflow는 프로젝트에서 재사용할 수 있는 학습과 결정을 아래 위치에 남깁니다.

```text
.unknowns-first/
  project-memory.md
  decisions.md
  resolved-unknowns.md
  open-unknowns.md
  question-log.md
```

이 파일들은 각 프로젝트의 runtime memory이므로, 이 plugin repository에서는 ignore됩니다.

## Source Layout

```text
.claude-plugin/plugin.json
.codex-plugin/plugin.json
skills/
  blindspot-pass/
  brainstorm/
  prototype/
  interview/
  reference/
  plan-and-notes/
  implement/
  explainer-quiz/
  memory-update/
  plan/       # compatibility alias
  closeout/   # compatibility alias
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
