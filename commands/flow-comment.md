---
description: Post a progress comment on a task
argument-hint: "<task-id> \"text\" [--commit]"
allowed-tools: Bash(flow comment:*), Bash(flow-comment:*)
---

Post a milestone update on the task with `flow comment $ARGUMENTS`. Add `--commit` (or `--commit=<sha>`) to attach a clickable diff of the work. Keep it to real progress the next agent can act on, not narration.
