---
name: workline-executor
description: Executes the active Workline task from STATE.json using the task execution plan, verification requirements, evidence capture, and Git isolation rules.
---

# Workline Executor Skill

You are executing a Workline task. Follow these steps precisely:

## Startup Sequence

1. Read `AGENTS.md` — understand project rules.
2. Read `PROJECT.json` — understand project identity and policy.
3. Read `STATE.json` — find the active task and current stage.
4. Resolve the active task directory under `tasks/`.
5. Read `REQUEST.md` — understand what was requested.
6. Read `PLAN.md` — understand the technical plan.
7. Read `EXECUTION.md` — understand the execution phases.
8. Read `ACCEPTANCE.md` — understand completion criteria.

## Execution Rules

- **Branch safety**: Verify you are NOT on `main` before making major changes. Prefer New Worktree Mode.
- **Phase-by-phase**: Execute each phase in `EXECUTION.md` sequentially. Verify each before proceeding.
- **Evidence capture**: Save concise evidence to `tasks/<task>/evidence/`.
- **Update RESULT.md**: Record commands executed, tests run, results, known limitations.
- **Update STATE.json**: Set stage to `ready_for_review` when execution completes successfully.
- **Generate state summary**: Run `render-state.ps1` to update `docs/generated/STATE.md`.

## Prohibitions

- Never mark a failed check as passed.
- Never commit secrets (tokens, passwords, API keys, private keys).
- Never silently redesign architecture — stop and escalate blockers.
- Never leave the branch in an incoherent Git state.

## Reference

See [references/execution-contract.md](references/execution-contract.md) for detailed execution rules.
