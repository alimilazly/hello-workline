# TASK-0002-verify-github-and-antigravity-integratio

## Task ID
TASK-0002-verify-github-and-antigravity-integratio

## Title
Verify GitHub and Antigravity integrations

## Requested Outcome
Turn every previously optional external integration into a real, evidenced acceptance run for the private hello-workline repository.

## Functional Requirements
- Install and authenticate the official GitHub CLI.
- Create a private GitHub repository and a Draft pull request.
- Observe the Workline metadata GitHub Actions job complete successfully.
- Configure main branch protection to require the metadata check when the GitHub plan permits it.
- Merge the pull request through GitHub and verify local main contains the reviewed commit.
- Install the official Antigravity CLI and execute a harmless headless prompt with machine-readable output.

## Non-Functional Requirements
- Keep credentials in native credential stores.
- Do not expose the repository publicly.
- Do not bypass Antigravity permission checks.
- Preserve durable command and API evidence in the task evidence directory.

## Explicit Non-Goals
- No production deployment or paid-plan purchase.
- No broad autonomous file modification by Antigravity.

## Constraints
- GitHub private-branch protection may depend on the authenticated account plan.
- Authentication screens must be completed by the account owner.

## User Acceptance Expectations
- Every requested external step has a real URL, API response, command result, or an explicit provider limitation.

## Open Questions
- None.
