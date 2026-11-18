---
type: talk-plain
event: React Summit
speaker: Tanner Linsley
date: 2026-11-17
relevance: Medium
takeaway: When you ask an AI to build something, naming a well-tested tool in your request saves it from making hundreds of hidden decisions you'd only discover one bug at a time.
tags:
  - conference-talk
  - plain-language
---
# Name Your Tools So the AI Doesn't Guess

**Speaker.** Tanner Linsley, creator of TanStack. React Summit, Nov 17.
**How much this matters to you.** Medium. Engineers usually pick the tools, but his list of problems an AI-built site runs into reads like an SEO checklist.

## The idea in plain words

Linsley makes TanStack, a family of free [libraries](../Glossary.md#library), meaning ready-made code that other people write, test and maintain so you don't have to. Weekly downloads are up 7.5 times in a year, and he credits AI for most of that. He ran short on time and skipped most of his demos, so parts of the talk got one sentence each.

His core line was "As code gets cheaper, trust gets more expensive." Anyone can ship an app now, and users can tell. One slide traced a user's trust going from "Love it" to "Lost my filters", "Spinner, again", "Charged twice" and finally "Gone."

Before AI, a team made many small decisions through specs, sketches and reading docs. Now AI jumps from idea to working software and makes those decisions itself. "Anywhere that you don't specify your intent ai is going to take creative liberty."

His fix is what he calls magic words. Writing "use React" or "use TanStack" in a [prompt](../Glossary.md#prompt), the request you type to the AI, pulls in "a decade or more worth of like edge cases and fixes and decisions and opinions" the AI would otherwise reinvent. Without that, "build me a website" looks great at first. Then the questions pile up. Can Google index it? Can AI bots read it? Where do meta tags go? Why is the first load blank? His slide said "AI can fix every one of these. You'll just find them one at a time." By week 8 his example had used 48 million [tokens](../Glossary.md#token), the units AI usage is billed in, plus $4,800 and 160 hours of your attention. He called it "decision debt."

He also showed TanStack Intent. Agents often remember an old way to use a library and invent options that don't exist. Intent ships the AI's instructions inside the library itself, so "The knowledge ships with the version you installed."

## Why it matters to web specialists

- His list of late surprises is your territory: indexing, AI crawlers, meta tags, a blank first load. An agent's first version can look done and still fail all four.
- He said his own [framework](../Glossary.md#framework), TanStack Start, handles content on first paint and per-page head tags. You only need to ask whether your project handles them.
- "Lost my filters" and "Spinner, again" are design failures. He mentioned keeping filters in the web address so the back button doesn't lose them.
- Writing intent in "excruciating detail" is what good design specs already do.

## What you can do with it

Our suggestions, not his.

- Before you ask an agent to build anything, ask an engineer which libraries and framework the project uses, and name them in your request.
- Check whether the project has a [CLAUDE.md](../Glossary.md#claudemd), a file of standing instructions the AI reads first. If those tool names aren't in it, ask an engineer to add them.
- Write the details you care about into the request. Empty states, loading states, error messages, page titles and descriptions.
- In a preview, use the back button after filtering. Reload a page and watch for a blank screen.
- Ask an engineer whether search engines and AI crawlers see the full content on first load.

His preview of TanStack Oracles, which he said is closer to writing tests in plain English, connects to [the talk on plain-English tests](16%20-%20Writing%20Tests%20in%20Plain%20English.md).

## Words worth knowing

- **Library.** Ready-made code for a common job, maintained by someone else.
- **Framework.** A larger library that sets the structure of a whole app.
- **Prompt.** The instruction you type to an AI.
- **Token.** The small chunks of text AI tools count and charge for.
- **CLAUDE.md.** A file of project rules that Claude Code reads before working.

## A line worth remembering

> "As code gets cheaper, trust gets more expensive."
> Tanner Linsley, on a slide
