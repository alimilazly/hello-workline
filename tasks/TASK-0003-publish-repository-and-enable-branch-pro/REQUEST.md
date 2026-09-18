# TASK-0003-publish-repository-and-enable-branch-pro

## Task ID
TASK-0003-publish-repository-and-enable-branch-pro

## Title
Publish repository and enable branch protection

## Requested Outcome
Apply the user's explicit decision to make the hello-workline GitHub repository public, enable enforceable protection on main, and preserve final API evidence.

## Functional Requirements
- Confirm the full Git history contains no common credential signatures before publication.
- Change `alimilazly/hello-workline` visibility to public.
- Protect `main` with strict `validate-metadata` checks.
- Enforce the rule for administrators and disable force pushes and deletion.
- Record GitHub API responses and merge this evidence through a protected pull request.

## Non-Functional Requirements
- Keep authentication tokens out of the repository.
- Do not weaken required checks to complete the task.
- Leave local and remote main synchronized and clean.

## Explicit Non-Goals
- No paid GitHub plan purchase.
- No unrelated source-code changes.

## Constraints
- The final evidence update must itself pass the protected PR workflow.

## User Acceptance Expectations
- The repository is publicly readable and GitHub reports active main protection.

## Open Questions
- None.
