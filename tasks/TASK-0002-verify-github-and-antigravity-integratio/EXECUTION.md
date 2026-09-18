# TASK-0002-verify-github-and-antigravity-integratio — Execution

## Phase 1 — Establish official clients and authenticated identity

### Preconditions
The local project and Workline root are clean and validation passes.

### Goal
Verify official client versions and authenticated account identities without exposing credentials.

### Files
Task evidence files only.

### Actions
1. Verify gh and agy versions.
2. Authenticate with native browser flows.
3. Read back public account identity and authentication status.

### Verification
Both binaries return a version and GitHub reports the expected active login.

### Evidence to Capture
Masked authentication status and version output.

### Success Criteria
Both official clients are callable; GitHub is authenticated.

### Failure Handling
Stop before external writes and retain the exact client error.

### Rollback
Use the clients' logout commands to clear cached sessions if requested.

## Phase 2 — Execute Antigravity headlessly

### Preconditions
agy is installed and authenticated.

### Goal
Run a harmless read-only prompt with JSON output in the project workspace.

### Files
tasks/TASK-0002-verify-github-and-antigravity-integratio/evidence/antigravity-headless.json

### Actions
1. Invoke agy with print mode and JSON output.
2. Parse the result as JSON.
3. Save the response as durable evidence.

### Verification
The process exits zero and the saved output parses as JSON.

### Evidence to Capture
CLI version, exit code, and JSON result.

### Success Criteria
A real model response is captured from headless mode.

### Failure Handling
Record authentication or provider failure and do not bypass permissions.

### Rollback
No project mutation is performed by the prompt.

## Phase 3 — Exercise hosted pull-request lifecycle

### Preconditions
The private remote exists and task results are committed on the task branch.

### Goal
Create a Draft PR, run Actions, configure protection, and merge through GitHub.

### Files
Task documents, evidence, STATE.json, and generated state summary.

### Actions
1. Push the task branch and create a Draft PR.
2. Wait for the Workline metadata Actions check.
3. Configure main protection using the observed check name.
4. Record review approval and acceptance evidence.
5. Merge through the guarded Workline GitHub path.

### Verification
GitHub API reports the PR, successful check, protection settings, and merged state; local main contains the reviewed commit.

### Evidence to Capture
Repository, PR, check-run, protection, and merge JSON responses.

### Success Criteria
The entire hosted lifecycle is evidenced, or a provider plan limitation is captured precisely.

### Failure Handling
Do not make the repository public or bypass a failed required check.

### Rollback
Close the PR if it has not merged; merged history is preserved as the acceptance record.
