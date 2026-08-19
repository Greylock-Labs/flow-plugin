---
description: Close a task with a summary the next agent can act on
argument-hint: "<task-id> \"summary\""
allowed-tools: Bash(flow close:*), Bash(flow-close:*), Bash(flow verify:*)
---

Close the task with `flow close $ARGUMENTS`. First make sure the work is verified (`flow verify` if it has tests). Write the summary against the task's ORIGINAL description - if any part of the described scope is unbuilt, say so and file a follow-up rather than closing it silently.
