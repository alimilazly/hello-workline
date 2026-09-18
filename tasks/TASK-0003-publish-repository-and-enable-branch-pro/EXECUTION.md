# TASK-0003-publish-repository-and-enable-branch-pro — Execution

## Phase 1 — Verify publication safety

### Preconditions
Local main is clean and equals origin/main.

### Goal
Confirm the complete Git history contains no common credential or private-key signatures.

### Files
Task evidence only.

### Actions
1. Enumerate all commits.
2. Scan tracked content by commit using filename-only matches.
3. Record the commit count and zero-match result.

### Verification
The scan returns no matching files.

### Evidence to Capture
Credential scan summary without secret values.

### Success Criteria
Zero credential-pattern matches.

### Failure Handling
Stop before publication and report matched paths.

### Rollback
No external change occurs in this phase.

## Phase 2 — Publish and protect main

### Preconditions
The scan passes and the user has explicitly authorized public visibility.

### Goal
Make the repository public and enforce the required metadata check on main.

### Files
GitHub repository settings and task evidence.

### Actions
1. Change visibility to public.
2. Configure strict required status checks for validate-metadata.
3. Enable administrator enforcement and discussion resolution.
4. Disable force pushes and branch deletion.
5. Read settings back through the API.

### Verification
GitHub reports PUBLIC visibility and the expected protection object.

### Evidence to Capture
Repository and protection JSON responses.

### Success Criteria
Every requested setting is present in the readback.

### Failure Handling
Do not claim protection until the API read succeeds.

### Rollback
Return visibility to private only on explicit user instruction.

## Phase 3 — Prove the protected PR path

### Preconditions
Protection readback succeeds.

### Goal
Merge the final evidence through a pull request after validate-metadata passes.

### Files
Task documents, evidence, STATE.json, and generated state.

### Actions
1. Create a Draft PR from the task branch.
2. Wait for validate-metadata.
3. Approve the Workline review.
4. Complete through the guarded GitHub merge path.

### Verification
The check succeeds and GitHub reports the PR merged into protected main.

### Evidence to Capture
PR and Actions URLs plus final branch-protection readback.

### Success Criteria
Protected main advances only through the successful PR.

### Failure Handling
Leave the PR open and keep main unchanged.

### Rollback
Close the unmerged PR if requested.
