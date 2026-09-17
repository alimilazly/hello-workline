# Hello Workline — AGENTS.md

## Roles

| Agent        | Role                     |
|--------------|--------------------------|
| Codex        | Architect + Planner + Reviewer |
| Antigravity  | Executor + Developer + Test Runner |

## Critical Rules

1. Read `PROJECT.json` for project identity and policy.
2. Read `STATE.json` for current dynamic state — it is the **only** canonical state source.
3. Read `docs/index.md` for project knowledge navigation.
4. Read the **active Task** docs before making changes.
5. **Never** perform major work directly on `main`.
6. **Never** store secrets in tracked files.
7. Run applicable verification before claiming completion.
8. Architecture decisions are recorded in `docs/decisions/` as ADRs. Accepted ADRs are not casually reversed.

## Navigation

- [PROJECT.json](PROJECT.json) — Stable identity
- [STATE.json](STATE.json) — Dynamic state
- [docs/index.md](docs/index.md) — Knowledge map
- [tasks/](tasks/) — Task directories

## Canonical Commands

```powershell
# From Workline root:
.\workline.ps1 status -Project "hello-workline"
.\workline.ps1 validate -Project "hello-workline"
.\scripts\render-state.ps1 -Name "hello-workline"
```
