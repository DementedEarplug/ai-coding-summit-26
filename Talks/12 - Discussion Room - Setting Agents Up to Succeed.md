---
type: talk-plain
event: React Summit + AI Coding Summit (discussion room)
speaker: Kent C. Dodds, Mark Erikson, Sarah (Redspace); moderator name unclear
date: 2026-11-17
relevance: Medium
takeaway: Give AI agents a short instruction file, turn your rules into automatic checks instead of long notes, and have agents write down what slowed them down so someone fixes it.
tags:
  - conference-talk
  - plain-language
---
# Discussion Room - Setting Agents Up to Succeed

**Speaker.** Kent C. Dodds, Mark Erikson of Replay.io, and Sarah of Redspace, with a moderator whose name is unclear. React Summit and AI Coding Summit discussion room, Nov 17.
**How much this matters to you.** Medium. It's aimed at engineers who set up agents, but two ideas, short instructions and writing down friction, apply to anyone who works with one.

These notes come from a Zoom recording transcribed by a speech-to-text tool that can't tell speakers apart. Points are credited to a person only when the transcript makes it clear. Kent Dodds arrived about 22 minutes in, and Mark Erikson left early to give his talk.

## The idea in plain words

The room discussed the [harness](../Glossary.md#harness), meaning everything you set up around the AI to get the output you want. Sarah defined it as "anything that you control above the LLM itself." Mark said an agent is "really just a while loop." It reads text, replies, runs a tool, and repeats. Tools like Claude Code are ready-made harnesses, and teams add their own rules on top.

Kent pushed hardest for keeping it small. "I refuse to add any process until I need it." The instruction file agents read first, AGENTS.md or [CLAUDE.md](../Glossary.md#claudemd), should be about 30 lines. His automated checks fail if his grows past that, "because agents just want to fill that thing up." He said too many instructions slow down newer AI models. Tell the agent the outcome you want, not the steps.

He also argued against relying on AI "memory." His example rule was "never use em dashes in emails." Instead of a memory, he'd make the email tool itself return an error when a draft breaks the rule. Mark made a related point. Agents forget instructions, so turn as many rules as you can into checks that always run the same way. Kent's order was types, then [lint rules](../Glossary.md#lint-rule), then tests, then a person checking by hand. Lint rules are automatic checks that flag code breaking a team rule.

The idea that stuck most was the [friction log](../Glossary.md#friction-log). Agents don't feel pain, Kent said. One loops for an hour, finds a workaround, and the next agent hits the same wall. So after each change ships, his agent writes down what slowed it down. Were the docs enough? Could it find things? Every night, agents fix the logged items. "Every single day it gets easier to work in this code base." Agents have even logged bugs outside their task, like a page showing `[object Object]`.

Agents also copy the patterns they see, so a consistent codebase is the best instruction. Kent writes down the reason behind each big decision so future agents know why, not only what.

## Why it matters to web specialists

- If an agent keeps getting your brand voice, spacing or heading rules wrong, a longer instruction file may not fix it. The panel's advice is a check that fails automatically.
- Your own notes on where the agent got stuck are a friction log. They're useful to whoever maintains the setup.
- Agents copy what's already there. If old pages use three styles of button, expect a fourth.
- Before the session, one panelist warned that agents' and people's needs "are going to diverge," and one spec for both could put agents ahead of people who rely on accessibility.

## What you can do with it

These are my suggestions, not the panel's.

- Keep a short friction log when you work with an agent. Note what it couldn't find, what it misread, and what you had to explain twice.
- When a rule matters, ask an engineer whether it can become an automatic check instead of a line in the instructions.
- Ask to see your team's agent instruction file. If it's hundreds of lines, raise Kent's 30-line point.
- Tell the agent the result you want, like "headings in sentence case," rather than a list of steps.

## Words worth knowing

- **Harness.** The setup around an AI: its instructions, tools and checks.
- **CLAUDE.md.** A file of standing instructions an agent reads at the start of every session.
- **Lint rule.** An automatic check that flags code or text breaking a team rule.
- **Friction log.** A running list of what slowed you or the agent down.
- **Deterministic.** Gives the same result every time. Code checks work this way and AI answers don't, see [deterministic](../Glossary.md#deterministic).

## A line worth remembering

> "A documented tool of deterministic code is going to be way better than a memory."
> Kent C. Dodds
