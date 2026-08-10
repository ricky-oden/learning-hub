# Repository Instructions

## Authoritative documents

- `docs/implementation-plan.md`
- `docs/status.md`
- `docs/decision-log.md`

## Mandatory plan alignment

Before implementation, review all authoritative documents and report:

- current `PLAN_VERSION`
- current phase
- requirement IDs addressed by the request
- allowed changes
- prohibited changes
- any conflict between the request and the approved plan

Do not replace or recreate the implementation plan. If a change is necessary, present it as `PROPOSED_CHANGE` and wait for explicit user approval before updating the plan or implementing the change.

## Scope and safety

- Do not push, create a pull request, deploy, or enable automatic CI triggers unless explicitly requested.
- Do not connect to paid or external services unless explicitly approved.
- Do not add features, dependencies, or architecture outside the approved plan.
- Preserve user changes and unrelated worktree changes.
- Keep implementation, tests, documentation, and requirement mapping synchronized.
- Never mark the project complete while required verification is failing or unexecuted.

## Quiz mode

When conducting a code-reading quiz:

- inspect current code before each question
- ask one question at a time
- do not reveal answers or target files before the user's answer
- preserve the user's answer verbatim
- distinguish repository-specific facts from standards, framework behavior, conventions, and alternatives
- update only `docs/code-reading-quiz-progress.md` unless the user explicitly requests code changes

