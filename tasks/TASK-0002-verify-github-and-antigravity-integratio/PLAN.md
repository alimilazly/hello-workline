# TASK-0002-verify-github-and-antigravity-integratio — Plan

## Task Goal
Prove the complete hosted lifecycle for hello-workline and prove that the official Antigravity CLI can run headlessly from the project.

## Current Repository Situation
The local project is validated and has a clean main branch. GitHub and Antigravity integrations exist locally, but the hosted lifecycle has not yet been exercised.

## Affected Components
- GitHub repository metadata and origin remote.
- Task control documents and evidence.
- STATE.json lifecycle fields.
- GitHub Actions and main branch protection.

## Design
Use a single bounded task branch. Capture Antigravity output before review, create a Draft PR from that branch, wait for the metadata workflow, enable protection, record approval, then merge through GitHub with an exact-head guard.

## Files Expected to Change
- PROJECT.json and STATE.json.
- Task documents and evidence under this task directory.
- Generated state summary.

## Dependencies
- Official gh CLI authenticated to github.com.
- Official agy CLI authenticated to the user's Antigravity account.

## Security Considerations
The repository remains private. Tokens are never printed or stored in project files. Antigravity retains its normal permission policy.

## Data / Migration Considerations
No application data migration is required.

## Risks
Private repository branch protection may be rejected on a GitHub Free plan. Actions or model service availability may delay validation.

## Rollback Strategy
Close an unmerged PR, leave main unchanged, and document the provider error. Local task evidence remains available for diagnosis.

## Decision Points
Require the check context reported by the real Actions run rather than assuming a name from configuration alone.

## Required ADRs
None; this verifies an already selected integration architecture.
