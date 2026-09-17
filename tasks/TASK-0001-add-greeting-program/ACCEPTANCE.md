# TASK-0001-add-greeting-program — Acceptance Criteria

## AC-001
Requirement: The greeting program exists at `src/hello.ps1`.
Verification: Check file exists.
Expected Result: File exists.
Required: Yes

## AC-002
Requirement: Running the program outputs "Hello from Workline".
Verification: Run `powershell -File src\hello.ps1` and check stdout.
Expected Result: Stdout contains exactly "Hello from Workline".
Required: Yes

## AC-003
Requirement: Task branch is not main.
Verification: Check `git branch --show-current`.
Expected Result: Branch name starts with `task/`.
Required: Yes

## AC-004
Requirement: RESULT.md contains execution evidence.
Verification: Read RESULT.md.
Expected Result: Non-placeholder content with test results.
Required: Yes