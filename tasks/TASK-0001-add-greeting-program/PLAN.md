# TASK-0001-add-greeting-program — Plan

## Task Goal
Create a minimal PowerShell script that prints "Hello from Workline" to validate the Workline framework task lifecycle.

## Current Repository Situation
Fresh project initialized with Workline template. No application code exists yet.

## Affected Components
- `src/` — new greeting script

## Design
A single PowerShell script `src/hello.ps1` that writes "Hello from Workline" to stdout.

## Files Expected to Change
- `src/hello.ps1` (NEW)

## Dependencies
- PowerShell (built-in)

## Security Considerations
None — no external access, no secrets.

## Risks
Minimal — trivial implementation.

## Rollback Strategy
Delete `src/hello.ps1` and revert the commit.

## Decision Points
None.