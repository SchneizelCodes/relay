---
name: utak-agent-handoff
description: "Use when work moves between AI tools or sessions (Claude Code, Codex, Gemini CLI, Cursor, Copilot) or to a second reviewer. Makes every tool follow the same rules, and packs a handoff with status, pointers, commands and a coverage checklist so the next agent continues instead of starting over. Triggers: hand this to Codex, continue in Gemini, second review, switch tools, save tokens by using another agent, context for the next session."
license: MIT
metadata:
  author: "SchneizelCodes (Joshua Manuel Camacho)"
  family: "utak"
  repo: "relay"
  version: "0.1.0"
---
# Hand work between agents

## Same rules everywhere
- One source of rules: `AGENTS.md` in the repo. `CLAUDE.md` contains `@AGENTS.md`; `GEMINI.md` says "Follow AGENTS.md."
- One memory: the vault. `utak activate --global` adds the vault loop to `~/.claude/CLAUDE.md`, `~/.codex/AGENTS.md`, `~/.gemini/GEMINI.md`.

## A handoff contains
1. **Entry prompt**: one paragraph the next agent can paste: goal, constraints, where to start.
2. **Status**: done / in progress / not started, using built, deployed, tested.
3. **Pointers**: files and lines, notes, docs. Not pasted contents.
4. **Commands**: how to run, test, build; the exact check that proves the task.
5. **Coverage list**: what was reviewed and what wasn't.
6. **Open decisions** and who makes them.

## Rules for the receiver
- Previous findings are claims to verify, not an answer key.
- Your own rerun counts; their old test result doesn't.
- Don't "fix" files another agent is still working on; say what you saw.
