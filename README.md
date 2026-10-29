<div align="center">

# Relay

**Better prompts in, better results out.**

![skills](https://img.shields.io/badge/skills-6-8b5cf6) ![format](https://img.shields.io/badge/format-Agent%20Skills-0ea5e9) ![license](https://img.shields.io/badge/license-MIT-22c55e) ![works with](https://img.shields.io/badge/works%20with-Claude%20Code%20%C2%B7%20Codex%20%C2%B7%20Gemini%20CLI%20%C2%B7%20Cursor-f59e0b)

</div>

Skills for the start and end of every task: read every part of the ask, write plain plans, record every update, remember your taste, hand work between agents, and save tokens without getting worse.

## Skills in this repo

| Skill | What it does | Switches on when you say |
|---|---|---|
| [`utak-agent-handoff`](skills/utak-agent-handoff/SKILL.md) | Use when work moves between AI tools or sessions (Claude Code, Codex, Gemini CLI, Cursor, Copilot) or to a second reviewer. Makes every tool follow the same rules, and packs a handoff with status, pointers, commands and a coverage checklist so the next agent continues instead of starting over. | hand this to Codex, continue in Gemini, second review, switch tools, save tokens by using another agent, context for the next session |
| [`utak-plain-plans`](skills/utak-plain-plans/SKILL.md) | Use when writing a plan, spec, proposal, PRD, policy, contract, terms or handoff that people must act on. Produces plain-language documents with Purpose, Scope, Status, and per-feature headings, every item labelled Approved, Proposed, Needs decision or Future. | write a plan, spec, proposal, roadmap, contract, terms, policy, feature brief |
| [`utak-read-the-ask`](skills/utak-read-the-ask/SKILL.md) | Use at the start of every non-trivial prompt, especially long, multi-part, numbered or messy ones. Extracts each separate request, decides who the output is for, loads the standing rules, and decides whether a question is really needed before acting. Prevents half-answered prompts. | multi-part requests, bug lists, feedback lists, 'also', numbered replies, voice-typed prompts |
| [`utak-record-updates`](skills/utak-record-updates/SKILL.md) | Use at the end of any task that changed a project: code, design, content, settings or decisions. Records the update so the next session and other agents can reuse it: project handoff entry, a reusable how-to note, the user's feedback as a lesson, and links. | done, wrap up, finish, before final reply, handoff, changelog, what did we change |
| [`utak-taste-memory`](skills/utak-taste-memory/SKILL.md) | Use whenever the user gives design, writing or product feedback (likes, dislikes, rejections, 'not like this', 'perfect, keep it') and at the start of any creative or UI task. Saves feedback as dated taste lessons and applies past lessons before producing new work, so the user never repeats the same feedback. | I don't like, too plain, too subtle, make it pop, perfect, keep this, redo, style, vibe, brand, design feedback |
| [`utak-token-saver`](skills/utak-token-saver/SKILL.md) | Use on long or expensive coding sessions to cut token use without losing quality: read slices not whole files, batch commands, keep context small, avoid re-deriving known facts, and measure compression tools before trusting them. | running out of tokens, usage limit, too expensive, context too long, slow session, save tokens, Caveman, RTK, compress context |

## Install

Skill IDs keep the `utak-` prefix across this collection. Keepsake also includes the memory CLI at `bin/utak.mjs`.

**Any agent, one command** (uses the open [`skills`](https://github.com/vercel-labs/skills) installer; it detects Claude Code, Codex, Cursor, Gemini CLI and dozens more):

```bash
npx skills add SchneizelCodes/relay -g            # all skills, for every project
npx skills add SchneizelCodes/relay -g --skill utak-agent-handoff   # just one
```

**Or copy by hand** (clone, then copy the folders in `skills/`):

| Agent | Put the skill folders in | Then |
|---|---|---|
| Claude Code | `~/.claude/skills/` (all projects) or `.claude/skills/` (one repo) | start a new session |
| Codex CLI | `~/.codex/skills/` or `.codex/skills/` | picked up on the next run |
| Gemini CLI | `~/.gemini/skills/` (or `~/.agents/skills/`) | `gemini skills enable <name>` |
| Cursor, Copilot, others | the agent's skills folder, or paste `SKILL.md` into its rules | |

```bash
git clone https://github.com/SchneizelCodes/relay
cp -r relay/skills/* ~/.claude/skills/        # Claude Code example
```

## Activate it on every prompt

Skills switch on by themselves when a task matches their description (that's the *Triggers* column above). To apply one on **every** prompt, name it in your agent's always-on instructions (`~/.claude/CLAUDE.md`, `~/.codex/AGENTS.md`, `~/.gemini/GEMINI.md`, or a repo's `AGENTS.md`):

```markdown
Always apply these skills: utak-agent-handoff, utak-plain-plans, utak-read-the-ask, utak-record-updates, utak-taste-memory, utak-token-saver.
```

You can also call one directly: in Claude Code type `/utak-agent-handoff`; in any agent, say "use utak-agent-handoff".

## Companion tools

Use one, or all four together. They share one vault and one loop.

**Planned:** Chorus (multi-model vault learning) and Guild (professional review agents). These two tools are not built or published yet.

| Repo | Category | In one line |
|---|---|---|
| [Keepsake](https://github.com/SchneizelCodes/keepsake) | Memory | A brain your coding agent can check. |
| [Touchstone](https://github.com/SchneizelCodes/touchstone) | Honest results | Stop your AI from overclaiming. |
| [Prism](https://github.com/SchneizelCodes/prism) | Think like a pro | Senior-engineer questions, on demand. |
| [Relay](https://github.com/SchneizelCodes/relay) | Prompt in, result out | Better prompts in, better results out. |

## Contributing

Ideas, fixes and new skills are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md): one skill per folder, a `SKILL.md` under 500 lines, a description that says what it does **and when to use it**, and a before/after example in the pull request. CI validates every skill against the [Agent Skills spec](https://agentskills.io/specification).

If Relay saved you a re-explained prompt, a ⭐ helps other developers find it.

## Credits and licence

Made by **Joshua Manuel Camacho** ([@SchneizelCodes](https://github.com/SchneizelCodes)), distilled from the private vault he uses to build Tindero, Kamayo and [his portfolio](https://joshua-camachodev.vercel.app). Only the methods are published here; no private project notes. MIT licence.
