---
name: ship-check
description: Pre-commit gate. Run tests, lint and type check; report PASS/FAIL per step and anything that could not run. Use before any commit or PR.
---

1. Read `CLAUDE.md` for the test / lint / typecheck commands.
2. Run each one. Capture the exit code and the last 20 lines of output.
3. Report a table: Step | PASS/FAIL | detail. A step that couldn't run is FAIL, never skipped silently.
4. If anything failed, say what to fix first. Don't fix it unless asked.
