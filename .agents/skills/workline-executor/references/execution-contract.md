# Workline Execution Contract

## Branch Safety

Before any major code changes, verify:

```
current branch != main
```

If on `main`, do NOT proceed with major work. Instead:
- Create or switch to the task branch (`task/TASK-NNNN-slug`).
- If branch creation is impossible, mark task as BLOCKED.

## Worktree Mode

Preferred execution mode is **New Worktree**:
- Antigravity creates an isolated worktree for the task branch.
- The primary working directory remains clean and recoverable.

If Antigravity creates a worktree branch with a different name than planned:
- Record the actual branch name in `STATE.json`.
- Do not force destructive renaming.
- Ensure the eventual PR still targets `main`.

## Phase Execution

1. Read the phase preconditions.
2. Execute the phase actions.
3. Run the phase verification.
4. Capture evidence listed in the phase.
5. Confirm success criteria before proceeding.
6. On failure: record the failure, diagnose, repair if safe, re-verify.

## Evidence Standards

- Save to `tasks/<task>/evidence/`.
- Prefer concise evidence (test summaries, build log excerpts, screenshots).
- Do not dump huge dependency logs into Git.
- Large/transient logs belong in `D:\workline\logs`.

## State Updates

After successful execution:
1. Update `RESULT.md` with: task ID, branch, commits, files changed, commands, tests, results, known limitations.
2. Update `STATE.json`: set `stage` to `ready_for_review`, update `verification` fields, set `updated_at`.
3. Generate `docs/generated/STATE.md` from `STATE.json`.

## Decision Points

If genuine uncertainty arises during execution:
- Define: trigger condition, allowed choices, evidence required, escalation rule.
- Do NOT silently redesign the system.
- Stop and report the blocker.

## Commit Standards

- Use conventional commit prefixes: `feat:`, `fix:`, `refactor:`, `test:`, `docs:`, `chore:`, `build:`, `ci:`.
- Prefer coherent, reviewable commits.
- Never commit secrets.
