# TASK-0003-publish-repository-and-enable-branch-pro — Acceptance Criteria

## AC-001
Requirement: Pre-publication history scanning finds no common credential signatures.
Verification: Scan every commit with filename-only credential patterns.
Expected Result: Zero matched files across all scanned commits.
Required: Yes

## AC-002
Requirement: The GitHub repository is public.
Verification: Read `visibility` and `isPrivate` through GitHub CLI.
Expected Result: Visibility is PUBLIC and isPrivate is false.
Required: Yes

## AC-003
Requirement: Main requires the validate-metadata check in strict mode.
Verification: Read branch protection through the GitHub API.
Expected Result: strict is true and validate-metadata is the required check.
Required: Yes

## AC-004
Requirement: Protection applies to administrators and blocks force push and deletion.
Verification: Inspect enforce_admins, allow_force_pushes, and allow_deletions.
Expected Result: Administrator enforcement is true; force push and deletion are false.
Required: Yes

## AC-005
Requirement: The evidence update follows the protected PR workflow.
Verification: Observe a successful validate-metadata check and GitHub merge.
Expected Result: The task PR passes Actions and merges into protected main.
Required: Yes
