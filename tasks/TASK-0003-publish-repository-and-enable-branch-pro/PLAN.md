# TASK-0003-publish-repository-and-enable-branch-pro — Plan

## Task Goal
Publish the verified repository, enable server-side main protection, and prove the final evidence can merge only after the required GitHub Actions check passes.

## Current Repository Situation
The repository was private on GitHub Free, where branch protection returned HTTP 403. The user explicitly chose to make it public so protection can be enabled.

## Affected Components
GitHub repository visibility, main branch protection, task evidence, RESULT.md, REVIEW.md, STATE.json, and generated state.

## Design
Scan all commits for common credential patterns, change visibility, configure protection through the GitHub API, read the settings back, then submit the evidence through a Draft PR governed by the new rule.

## Files Expected to Change
Only this task's documents and evidence plus Workline state files.

## Dependencies
Authenticated GitHub CLI and the existing validate-metadata workflow.

## Security Considerations
Publication exposes complete Git history. The pre-publication scan must report zero credential-pattern matches.

## Data / Migration Considerations
No application data migration is involved.

## Risks
Publication is externally visible. The user explicitly authorized this visibility change.

## Rollback Strategy
Repository visibility can be returned to private, but copies made while public cannot be recalled. Protection can be read and adjusted through the GitHub API.

## Decision Points
Require the real Actions check context `validate-metadata` and keep administrator enforcement enabled.

## Required ADRs
None; this is an operational repository setting.
