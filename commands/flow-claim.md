---
description: Claim a task before you start working on it
argument-hint: "<task-id> [--files=a,b] [--checkout]"
allowed-tools: Bash(flow claim:*), Bash(flow-claim:*), Bash(flow show:*)
---

Claim the task with `flow claim $ARGUMENTS` so no other agent picks it up. Then read it in full with `flow show <task-id>` and start the work. Pass `--files=` with the paths you expect to touch so Flow can warn about collisions, and `--checkout` to switch onto the task branch.
