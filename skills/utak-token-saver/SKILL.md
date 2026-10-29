---
name: utak-token-saver
description: "Use on long or expensive coding sessions to cut token use without losing quality: read slices not whole files, batch commands, keep context small, avoid re-deriving known facts, and measure compression tools before trusting them. Triggers: running out of tokens, usage limit, too expensive, context too long, slow session, save tokens, Caveman, RTK, compress context."
license: MIT
metadata:
  author: "SchneizelCodes (Joshua Manuel Camacho)"
  family: "utak"
  repo: "relay"
  version: "0.1.0"
---
# Save tokens without getting dumber

## Habits that save the most
- **Search, then read slices.** grep/glob for the line, read 40 lines around it. Never dump a whole large file.
- **Don't reread** files you already have in context.
- **Batch** independent commands in one call; run long builds and tests in the background while you write.
- **Small context**: load the 3 best notes, not the folder. Trim old tool output you no longer need.
- **One script for many mechanical edits**, then one typecheck.
- **Stop exploring once you can act.**
- **Remove unused MCP servers and giant system prompts**: they cost tokens on every turn.

## Compression tools: measure first
Proxies and "terse" skills advertise 20–90% savings; independent tests have found far less on real tasks. Before adopting one, run the same 5 tasks with and without it and compare tokens *and* correctness. Never put a lossy compressor in front of exact IDs, hashes, amounts or secrets.

## Replies
Answer first; then what changed; then the user's next steps. No restating the plan.
