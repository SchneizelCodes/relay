---
name: utak-taste-memory
description: "Use whenever the user gives design, writing or product feedback (likes, dislikes, rejections, 'not like this', 'perfect, keep it') and at the start of any creative or UI task. Saves feedback as dated taste lessons and applies past lessons before producing new work, so the user never repeats the same feedback. Triggers: I don't like, too plain, too subtle, make it pop, perfect, keep this, redo, style, vibe, brand, design feedback."
license: MIT
metadata:
  author: "SchneizelCodes (Joshua Manuel Camacho)"
  family: "utak"
  repo: "relay"
  version: "0.1.0"
---
# Taste memory

The user's taste is the most expensive thing to re-explain. Capture it once, apply it forever.

## When feedback arrives
- Write one line in `lessons/Taste lessons.md` (or a project's own lessons note): date, what was rejected or praised, and the rule it implies.
  - Illustrative examples (replace the date and wording with the user's actual feedback):
    - `YYYY-MM-DD: long paragraphs rejected; use short sections with clear headings.`
    - `YYYY-MM-DD: dense dashboard rejected; show the main action before optional details.`
    - `YYYY-MM-DD: checkout layout approved; preserve it unless the user requests a change.`
- Approved designs are **locked**: list them so no agent "improves" them uninvited.

## Before creative work
- Read the lessons for this project and the shared ones.
- Say which lessons you're applying in one line.
- When a new request conflicts with a lesson, the new request wins; update the lesson.

## Keep it useful
Rules, not transcripts. Merge duplicates. Remove lessons the user reverses.
