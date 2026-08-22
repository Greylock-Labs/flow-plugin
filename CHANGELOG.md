# Changelog

All notable changes to the Flow Collab plugin for Claude Code.

## 0.1.0 - 2026-08-21

- Initial release.
- SessionStart hook that injects your Flow board identity + assigned tasks each session and keeps the team CLAUDE.md in sync, via the published `flowcollab` CLI.
- Eight slash commands: pull, next, claim, show, comment, verify, close, whoami.
- Install with `/plugin marketplace add Greylock-Labs/flow-plugin` then `/plugin install flowcollab@flowcollab`.
