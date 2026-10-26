---
name: agent-operator
description: Decision guide for running Claude Code work in parallel. Covers subagents, agent view, agent teams, cross-session messaging, dynamic workflows, and worktrees. Use when the owner says "run these in parallel", "make a subagent", "which approach should I use", "should this be a team or a subagent", "use a worktree", or asks how any of these features work.
---

Source: the official Claude Code docs (https://code.claude.com/docs), summarized in Oct 2026. Features are marked research preview or experimental where the docs say so. Behavior changes between versions: check `claude --version` and the docs index at https://code.claude.com/docs/llms.txt before relying on a detail. This file is a decision guide only. The docs are the reference.

## The five ways to run work in parallel

| Approach | Who coordinates | Use it when |
| :- | :- | :- |
| Subagents | Claude, inside one session | A side task would flood the main chat with search results, logs or file contents |
| Agent view | You (dispatch, check back later) | Several independent tasks, handed off and monitored from one screen |
| Agent teams (experimental, off by default) | A lead Claude | Workers need to talk to each other and share a task list |
| Dynamic workflows | A script | A job outgrows a handful of subagents, or findings need cross-checking |
| Cloud projects | Claude, in the cloud | Work spans days or weeks and should run with the machine off |

Supporting tools, not ways to run agents by themselves:
- Worktrees: a separate git checkout per session so edits never collide.
- Cross-session messaging: sessions pass findings to each other.
- `/batch`: splits one big change into many worktree-isolated subagents.

## Decision guide

Ask these three questions in order:

1. Who coordinates?
   - Claude delegates and collects inside one chat: subagents.
   - I hand off tasks and check back: agent view.
   - Claude plans, assigns and supervises peers: agent teams.
   - A script holds the plan: dynamic workflow.
2. Do the workers need to talk to each other?
   - No, they report back: subagents or agent view.
   - Between sessions I run myself: cross-session messaging.
   - Directly, with a shared task list: agent teams.
3. Do they touch the same files?
   - Yes: use worktrees. Agent teams do not isolate files, so give each teammate different files.

Rules of thumb:
- Default to the main conversation for quick, back-and-forth work. Parallelism has overhead.
- Parallel runs multiply token usage. Say so before launching anything big.
- Start with research or review tasks before parallel code edits.
- Subagents start blank. They only know their own file and the prompt Claude writes for them.

## How this team uses it
- The agents in this repo are subagents. Each is one markdown file with its own tools and model.
- Review roles (QA, security) run as separate subagents so the builder never grades its own work.
- Anything that sends, books, or publishes stays behind a human approval step, whichever approach is used.

## Quick command index
- `claude agents` opens agent view. `claude --bg "prompt"` starts a background session.
- `/bg` sends the current session to the background.
- `/tasks` lists background items in this session.
- `claude --worktree <name>` starts in an isolated worktree.
- `claude --agent <name>` runs the whole session as a subagent.
- `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1` enables agent teams.
