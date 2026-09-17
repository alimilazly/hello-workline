# TASK-0001-add-greeting-program — Execution

## Phase 1 — Implementation

### Preconditions
- On task branch (not main).
- Project structure valid.

### Goal
Create the greeting program.

### Files
- `src/hello.ps1` (NEW)

### Actions
1. Create `src/` directory.
2. Create `src/hello.ps1` with content: `Write-Output "Hello from Workline"`
3. Commit with message `feat: add greeting program`.

### Commands
```powershell
New-Item -Path src -ItemType Directory -Force
Set-Content -Path src\hello.ps1 -Value 'Write-Output "Hello from Workline"' -Encoding UTF8
git add -A
git commit -m "feat: add greeting program"
```

### Verification
Run `powershell -File src\hello.ps1` and verify output is "Hello from Workline".

### Evidence to Capture
- Runtime output saved to `evidence/runtime-output.txt`.

### Success Criteria
- Script exists and runs without error.
- Output matches expected string.

### Failure Handling
If script fails, check PowerShell syntax.

### Rollback
`git revert HEAD`

## Phase 2 — Verification

### Preconditions
Phase 1 complete.

### Goal
Verify acceptance criteria and capture evidence.

### Actions
1. Run the greeting program.
2. Capture output to evidence file.
3. Verify output matches expected string.
4. Update RESULT.md.

### Commands
```powershell
powershell -File src\hello.ps1 | Tee-Object -FilePath tasks\TASK-0001-add-greeting-program\evidence\runtime-output.txt
```

### Verification
Evidence file contains "Hello from Workline".

### Success Criteria
All acceptance criteria satisfied.

### Failure Handling
Re-examine Phase 1 implementation.

### Rollback
Not applicable for verification phase.