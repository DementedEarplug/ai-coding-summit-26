---
type: talk-plain
event: AI Coding Summit
speaker: Kaleb McKelvey
date: 2026-11-17
relevance: High
takeaway: A developer's wife, who works in finance, now fixes bugs in their app by describing them to Claude, and that only works because he first built the rules and checks around the AI.
tags:
  - conference-talk
  - plain-language
---
# A Non-Developer Ships Fixes with Claude

**Speaker.** Kaleb McKelvey, Netflix. AI Coding Summit, Nov 17.
**How much this matters to you.** High. This is your situation, a non-coder fixing a real app with an AI agent, told by the engineer who set it up. Read this one first.

## The idea in plain words

McKelvey's wife works in finance and is learning Spanish by listening only. She logged more than 1,500 hours in a spreadsheet with forecasts. In February he decided to turn that spreadsheet into an app.

He started by [vibe coding](../Glossary.md#vibe-coding), prompting Claude without caring how the code was built. He gave it the spreadsheet and said "turn this into an app." It reached the App Store in three weeks. Then the code got messy. One screen file hit 769 lines, one form needed 21 database queries, and every chat started from scratch. Claude stopped understanding the app.

So he rebuilt it around a [harness](../Glossary.md#harness), the instructions, rules and automatic checks around the AI. His [CLAUDE.md](../Glossary.md#claudemd), the instruction file Claude reads first, is a 120-line map pointing to docs on architecture, design, patterns and the database. It governs 75,000 lines of code. One rule reads "You're not allowed to use your own hex values anymore. Please, please use the theme." His design docs, with tokens, screens and user journeys, live in a Claude Design artifact he points Claude at before building something new. [Hooks](../Glossary.md#hook), scripts that run automatically at set moments, keep Claude away from secret files and run checks after every edit and before every push.

Now when his wife finds a bug, he sends her a link to a Claude Code session. She describes it with screenshots, Claude fixes it, and the new version goes to her test copy of the app to check. One recent fix was a stats page that didn't refresh after a new log. The app has had 12 releases and about 250 total users, of whom he said about 5 are active. His wife has logged 2,262 hours of Spanish.

The talk was watched as a replay on Nov 18, through a Whisper transcript and slide photos.

## Why it matters to web specialists

- His wife ships fixes without being a developer. But an engineer built the rules, checks and test setup first. That setup is what makes it safe.
- His hex value rule is a design system rule written for an AI. Your tokens and patterns can be rules like that.
- He still worries. Another talk taught him Claude can change its own hooks to get around them. He may move the checks where Claude can't edit them, and he runs it on a separate Mac mini.
- On apps with sensitive data, he said it depends on the risk you accept. A system first responders use is maybe not one AI should build.

## What you can do with it

These are my suggestions, not his.

- Before fixing anything with an agent, ask an engineer what's in place. Is there a CLAUDE.md map, automatic checks before release, and a test copy you can try first?
- Report bugs the way his wife does, with what you did, what you expected, what happened and screenshots.
- Write design rules as short sentences like his hex rule, and ask an engineer to add them to the map.
- Test every fix yourself in a preview before release.
- Ask what the worst thing your change could break is. Payment, login and private data deserve an engineer's review.

## Words worth knowing

- **Vibe coding.** Building by prompting an AI without looking at the code.
- **Harness.** The instructions, rules and automatic checks around an AI agent.
- **CLAUDE.md.** A file of instructions Claude reads at the start of every session.
- **Hook.** A script that runs automatically at a set moment, like after every edit.

## A line worth remembering

> "It really is dependent on the risk that you're willing to accept."
> Kaleb McKelvey
