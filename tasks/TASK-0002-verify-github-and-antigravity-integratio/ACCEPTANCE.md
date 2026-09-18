# TASK-0002-verify-github-and-antigravity-integratio — Acceptance Criteria

## AC-001
Requirement: The private GitHub repository exists under the authenticated account and origin points to it.
Verification: Read repository visibility and URL through gh, then compare git remote origin.
Expected Result: alimilazly/hello-workline is private and origin uses its HTTPS URL.
Required: Yes

## AC-002
Requirement: A Draft PR exists for the bounded task branch.
Verification: Read the PR through gh and confirm isDraft is true before review completion.
Expected Result: The PR is open, draft, and targets main.
Required: Yes

## AC-003
Requirement: The Workline metadata GitHub Actions job runs successfully on the PR.
Verification: Read check-run status and conclusion for the PR head commit.
Expected Result: The validate-metadata check completes with success.
Required: Yes

## AC-004
Requirement: Main branch protection requires the observed metadata check when supported for the private repository.
Verification: Read branch protection through the GitHub API.
Expected Result: Protection is enabled with strict required checks, or the exact plan limitation is documented as a provider constraint.
Required: Yes

## AC-005
Requirement: The official Antigravity CLI completes a headless JSON response in the project.
Verification: Parse the saved headless output and record the CLI exit code.
Expected Result: agy exits zero and emits valid JSON from a real model response.
Required: Yes

## AC-006
Requirement: The PR merges through GitHub only after checks pass, and local main contains the reviewed task commit.
Verification: Read PR merged state and verify Git ancestry locally.
Expected Result: GitHub reports MERGED and local main contains the task head.
Required: Yes
