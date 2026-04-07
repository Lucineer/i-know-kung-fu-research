# I Know Kung Fu: Claude Code Research

> "I know Kung Fu."  
> "Show me."  
> — Neo & Morpheus, The Matrix (1999)

This repository documents a systematic investigation into Claude Code's internals using a real wifi driver codebase. It traces what happens when you add a Skill file—from tokenization to execution—with observable, testable examples.

Part of Cocapn Fleet open-source agent research.

## Why this exists

Most Claude Code tutorials show what to type. Few explain why it works. This project answers practical questions:

- Why does a 20-line Skill file change Claude's behavior?
- When do Hooks actually run?
- What happens when you create an Agent file?
- Why does Claude sometimes follow rules then forget?

No official documentation covers this. We built reproducible tests instead of theories.

## What this covers

1. **LLM Fundamentals** – Only what matters: tokens, context windows, and why Claude misses rare variable names.
2. **Claude Code Internals** – Map of how files are processed and when each component loads.
3. **CLAUDE.md** – How project memory works and when it's read.
4. **Skills** – How small files produce large behavioral shifts.
5. **Subagents** – How Claude delegates to specialized roles.
6. **Hooks** – The hard rules that persist across conversations.
7. **Failure Cases** – Intentional breakpoints showing system limitations.

## One honest limitation

This research is based on reverse-engineering current behavior. Claude Code's internals may change without notice, and some findings are version-dependent.

## Quick start

1. Fork this repository.
2. Open the wifi driver codebase in Claude Code.
3. Run the test cases in `tests/` to see each mechanism in action.
4. Modify the Skill files and observe changes.

Each test includes expected outcomes and explanations of what's happening internally.

## Structure

- `skills/` – Example Skills showing different activation patterns
- `hooks/` – Hook implementations with timing tests
- `agents/` – Subagent definitions and call traces
- `tests/` – Runnable test cases with observations
- `wifi-driver/` – Real production code used as test base

## Attribution

Research by Superinstance & Lucineer (DiGennaro et al.). MIT licensed. Runs on Cloudflare Workers.

---

Part of [Cocapn Fleet](https://the-fleet.casey-digennaro.workers.dev) • [Cocapn](https://cocapn.ai)  
Fork-first open source agent research.