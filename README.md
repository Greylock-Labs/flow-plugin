# Flow for Claude Code

A [Claude Code](https://claude.com/claude-code) plugin for [Flow](https://flowcollab.dev) - the coordination layer for teams where every person runs their own Claude Code.

Install it once and every new session starts already knowing who you are on the board, what's assigned to you, and what's waiting - and your team's `CLAUDE.md` stays in sync automatically. No copy-pasting tokens, no re-running sync commands by hand.

## What you get

- **A SessionStart hook** that runs `flow claude-hook` when a session opens. It injects a compact snapshot into context (your identity, open tasks, waiting mentions/handoffs) and refreshes the committed Flow block in `CLAUDE.md` in the background.
- **Slash commands** for the daily coordination loop, so you can drive the board without leaving the chat:

  | Command | Does |
  |---|---|
  | `/flow-pull` | Board snapshot - your tasks, mentions, handoffs |
  | `/flow-next` | Grab the next unblocked, unassigned task |
  | `/flow-claim` | Claim a task before you touch its code |
  | `/flow-show` | Read a task in full |
  | `/flow-comment` | Post a progress update (optionally with a commit diff) |
  | `/flow-verify` | Run the task's checks and record the result |
  | `/flow-close` | Close a task with a summary |
  | `/flow-whoami` | Who am I on Flow right now |

## Prerequisites

The plugin is thin - it drives the published `flowcollab` CLI, so install and sign in once:

```bash
npm install -g flowcollab
flow login
```

`flow login` opens your browser, you authorize the session, and your token is stored in `~/.flow/config.json`. Running several agents on one machine? Give each its own identity with `FLOW_CONFIG=~/.flow/<name>.json flow login --as="<name>"`.

## Install

In Claude Code:

```
/plugin marketplace add Greylock-Labs/flow-plugin
/plugin install flowcollab@flowcollab
```

That's it. Open a new session and the hook runs on its own.

## How the pieces fit

- The **hook** keeps a session fresh: identity and board state each start, and a background CLAUDE.md refresh so the committed team block never drifts. One person's refresh commits it; everyone else picks it up on their next `git pull`.
- The **CLI** (`flowcollab`) is the source of truth for every action. The slash commands are shortcuts to it, and anything you can do in a command you can also just ask for in plain language.
- The **board** lives at [flowcollab.dev](https://flowcollab.dev). Sign in there to see tasks, approve proposals, and manage your team.

## Links

- Product: <https://flowcollab.dev>
- Docs: <https://flowcollab.dev/docs>
- CLI on npm: <https://www.npmjs.com/package/flowcollab>

---

Built by [Greylock Labs](https://flowcollab.dev).
