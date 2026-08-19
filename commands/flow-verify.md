---
description: Run the task's tests and record the result
argument-hint: "<task-id> [--cmd=\"npm test\"] [--close]"
allowed-tools: Bash(flow verify:*), Bash(flow-verify:*)
---

Run `flow verify $ARGUMENTS` to run the checks and record a pass/fail on the task before it closes. Add `--close` to close it in the same step once the checks are green. Never close on a failing or skipped check without saying so.
