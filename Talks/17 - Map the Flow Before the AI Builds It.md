---
type: talk-plain
event: React Summit
speaker: David Khourshid
date: 2026-11-17
relevance: High
takeaway: Asking an AI to copy or rebuild an app straight from a prompt fails, and drawing every screen, action and hidden condition first is what made it work.
tags:
  - conference-talk
  - plain-language
---
# Map the Flow Before the AI Builds It

**Speaker.** David Khourshid, founder of Stately.ai. React Summit, Nov 17.
**Technical notes.** [[17 - Cloning Full-Stack Apps with AI|Full technical version]]
**How much this matters to you.** High. His fix is a user flow diagram with rules attached, which is work designers already know how to do.

## The idea in plain words

Khourshid spent 8 months copying more than 100 real apps, so AI agents could train in fake versions of them. It cost thousands of dollars in [[Glossary#Token|tokens]], the units AI usage is billed in. A new app only has to "work," which he called a feeling. A copy has to match the original exactly.

His first try was to give an [[Glossary#Agent|AI agent]] the app, tell it to "Clone it," and add "Make no mistakes." That failed three ways. A whole app overflowed the [[Glossary#Context window|context window]], the amount of text the AI can hold at once. His slide showed 1,847,203 tokens against a 200,000 limit. Loose prompts missed behavior, so a screen matched but applying a coupon did nothing behind it. And a strict [[Glossary#Spec|spec]], a written description of what the app must do, failed apps that were good enough to improve.

A screen isn't the whole story. In his Starbucks example, picking a grande or a venti changes the pixels but not what happens next. The reverse also happens. Pick a latte first and "add" asks you to choose a cafe. Pick the cafe first and the same screen takes you to your cart.

What worked was a map between the prompt and the code. For screens he used [[Glossary#Statechart|statecharts]], diagrams of every state a user can be in and every action that moves them on. For the server side he wrote plain-sentence contracts for the data and each request. He calls this layer a model, a different thing from an AI model. Every rule pointed to evidence, a recording of the real app doing that thing. The evidence was the truth, and the map was a guess to check against it. Round by round, the copy got close to perfect, at least for what he could observe.

He also announced free Stately [[Glossary#Skill|skills]], add-on instructions that help agents draw these statecharts. These notes come from a Whisper transcript, which got stuck on one line for about a minute near the start, so the opening comes from his slides.

## Why it matters if you design or do SEO

- A statechart is a user flow with the hidden conditions written in. If you draw loading, error and success states, you're halfway there.
- His bug example was a rental booking where you could press reserve while the price was still loading. Designers catch bugs like that in previews.
- He said a migration done from a prompt alone will change behavior "even if all the tests pass." Someone has to write down the old behavior first.
- SEO people will know his crawler history. Once pages changed without the URL changing, the URL stopped describing what the visitor sees.

## What you can do with it

These are my suggestions, not his.

- Before an agent builds or rebuilds a flow, list every screen, every action and where it leads, including what earlier choices change.
- Mark which rules you saw in the real product and which are guesses, with screenshots as evidence.
- On a redesign, ask the agent to list the old version's behavior first, and check that list yourself.
- Ask the agent where a user can act at the wrong moment, like reserving before the price loads.

## Words worth knowing

- **Statechart.** A diagram of every state a flow can be in and the actions between them.
- **Context window.** How much text the AI can keep in mind at once.
- **Spec.** A written description of what the software must do.
- **Skill.** A packaged set of instructions an agent loads for one kind of task.

## A line worth remembering

> "Instead, the evidence is the source of truth. And the model or the specification is just a hypothesis on that."
> David Khourshid
