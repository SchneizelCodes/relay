---
name: utak-record-updates
description: "Use at the end of any task that changed a project: code, design, content, settings or decisions. Records the update so the next session and other agents can reuse it: project handoff entry, a reusable how-to note, the user's feedback as a lesson, and links. Triggers: done, wrap up, finish, before final reply, handoff, changelog, what did we change."
license: MIT
metadata:
  author: "SchneizelCodes (Joshua Manuel Camacho)"
  family: "utak"
  repo: "relay"
  version: "0.1.0"
---
# Record every update

Work that isn't written down is re-done. Before the final reply, record:

1. **Handoff entry** in `projects/<name>/<Name> handoff.md` (newest first):
   `## <date>: <what changed>` · files/commit · why · how it was verified · what's next.
2. **Reusable how-to** in a shared folder for anything another project could use: the pattern, copy-ready code, gotchas, how it was verified. Search first; improve an existing note if one owns it.
3. **Feedback as a lesson** in `lessons/`: what the user rejected and what they wanted instead, in their words, with the date. ("Too subtle" → "motion must be visible at a glance".)
4. **Links both ways**, and run `utak check`.

Then say in the reply which notes you wrote. Don't commit or push the vault unless the user asked.

Skip it when nothing reusable happened. A typo fix doesn't need a note.
