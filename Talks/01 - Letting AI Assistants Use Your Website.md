---
type: talk-plain
event: JSNation
speaker: Wes Bos
date: 2026-11-16
relevance: High
takeaway: A website can hand an AI assistant a list of the actions it supports, so the assistant does them in the same open tab instead of guessing from screenshots.
tags:
  - conference-talk
  - plain-language
---
# Letting AI Assistants Use Your Website

**Speaker.** Wes Bos. JSNation, Nov 16.
**Technical notes.** [[01 - WebMCP - Clicks and Clankers|Full technical version]]
**How much this matters to you.** High. If assistants start using websites for people, the names, labels and descriptions you write become the instructions they follow.

## The idea in plain words

Today, when an AI [[Glossary#Agent|agent]] uses a website for you, meaning an AI that clicks and types on your behalf, it works like a stranger. It takes screenshots, reads the page and guesses which button to press. Wes Bos says this is slow, costs a lot and breaks often. [[Glossary#WebMCP|WebMCP]] is a proposed web standard where the page gives the agent a list of things it can do. You ask in plain English, like "turn the rack red," and the agent calls those actions directly. His summary was "Cheaper, faster, and less flaky."

He built a 3D gym builder, then realized he didn't want to learn its buttons. So he turned every action, about 89 of them, into a named tool. In a recorded demo a voice agent resized the room, placed a treadmill and changed the theme. It made mistakes, like overlapping pieces, and fixed them when he corrected it in plain language.

The part he cares about most is sharing. You and the agent work in the same open tab at the same time, and the page updates as the agent works. He calls this "clicks and clankers." The agent uses the login you already have. He thinks it fits visual tools best, like video editors, where you still want to drag things yourself.

It is early. Chrome and Edge have it as a trial, and Safari has nothing. One caveat. These notes come from auto-generated transcripts that start partway into the talk, and the first Q&A question was cut off.

## Why it matters if you design or do SEO

- Each tool has a name and a plain-language description. Someone has to write those, and it is closer to UX writing than to code.
- Without WebMCP, agents read the page's [[Glossary#Accessibility tree|accessibility tree]], the map of labels and roles that screen readers use, or they take screenshots. In the Q&A he said this works but is slow and wastes [[Glossary#Token|tokens]], the units AI use is billed in. So today's agents lean on the labels you already write.
- His "just find the setting" example was a big vendor dashboard where you ask "where do I block crawlers?" and the agent switches it on. That is a findability problem, and findability is your field.
- Not every company wants this. He named Amazon and airlines, which profit from upsells at checkout. "Airlines don't want to be a utility."
- Reviews and comments from strangers can hide instructions aimed at the AI. This is called [[Glossary#Prompt injection|prompt injection]]. WebMCP has a hint to flag that text, but he said it is not a security layer. Asked about banking apps, he said "I know some people are going to get pwned."

## What you can do with it

These are my suggestions, not the speaker's.

- Ask an engineer whether your product plans to support WebMCP or AI agents. If yes, offer to write the tool names and descriptions.
- Turn on a screen reader on one of your key pages and listen to the labels. That is close to what an agent reads today. Vague labels like "Click here" hurt both groups.
- List the five tasks people most often fail to find in your product. Those make good first tools.
- For anything that spends money or deletes data, ask that the user must confirm it. The speaker described a "consequential" hint built for this.

## Words worth knowing

- **Agent.** An AI that takes actions for you, like clicking or editing, instead of only chatting.
- **WebMCP.** A proposed standard where an open web page lists the actions an AI is allowed to call.
- **Accessibility tree.** The browser's map of every label and role on a page. Screen readers use it, and so do AI agents.
- **Prompt injection.** Hidden instructions inside normal text, like a product review, that try to trick the AI.

## A line worth remembering

> "Your skill should be in designing it, your skill should not be in knowing which buttons to click."
> Wes Bos
