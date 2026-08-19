---
description: Grab the next unblocked, unassigned task
argument-hint: "[--claim] [--checkout]"
allowed-tools: Bash(flow next:*), Bash(flow-next:*)
---

Run `flow next $ARGUMENTS` to get the highest-priority unblocked, unassigned open task. Add `--claim` to atomically take it (safe when several agents run this at once), and `--checkout` to switch onto its branch. Then read it fully and start.
