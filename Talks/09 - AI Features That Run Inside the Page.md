---
type: talk-plain
event: AI Coding Summit
speaker: Navya Agarwal
date: 2026-11-16
relevance: Medium
takeaway: A web page can tell AI assistants exactly what actions it offers, and the browser itself can now run small AI models, so not every AI feature needs an expensive server.
tags:
  - conference-talk
  - plain-language
---
# AI Features That Run Inside the Page

**Speaker.** Navya Agarwal, Adobe. AI Coding Summit, Nov 16.
**How much this matters to you.** Medium. The tools are early and mostly Chrome-only, but they change how your forms, labels and page content get read by AI assistants.

These notes come from a recording with no audio. Everything here is from the slides, the demo videos and the question board. The spoken answers to audience questions are missing.

## The idea in plain words

Teams feel pushed to bolt an AI assistant onto every product, and someone pays for every word the AI reads and writes. Agarwal asked whether an AI feature has to start with a big AI model running on a company server. Her answer was no, and she showed two browser features that skip the server.

The first is [WebMCP](../Glossary.md#webmcp), a proposed web standard that lets a page publish a list of actions an AI assistant can take, like "add slides" or "book a slot." Today an [agent](../Glossary.md#agent), meaning an AI that takes actions for you, often works by looking at screenshots and clicking at screen positions. Her slide called the result "probabilistic." It breaks when the layout changes, and finishing the clicks doesn't prove the goal was met. Her point was simple. "The application already knows what actions it supports." So let it say so.

She demoed this on her own slide deck, which offered six actions. An assistant in the browser added eight slides, switched the theme and renamed a slide using only those actions. A second agent running in a terminal did the same, and every action went through an approval check first.

The second feature is Chrome's built-in AI, a form of [on-device AI](../Glossary.md#on-device-ai), meaning the AI runs on the visitor's own computer. Chrome ships small task tools for summarizing, translating, detecting language, writing, rewriting and proofreading. Her deck summarized itself and translated a slide into French, all locally. Summarizer, Translator and Language Detector are in Chrome 138. Writer, Rewriter and Proofreader are still trials.

She was careful about limits. WebMCP is "Proposed web standard, not final." Firefox and Safari had no support listed. Her idea that cheaper, local [models](../Glossary.md#model) could handle routine tasks was labeled "Hypothesis. Not measured." One more caveat comes from a later talk. The version that worked by adding labels to ordinary HTML forms has since been removed from the spec, per [Letting AI Assistants Use Your Website](01%20-%20Letting%20AI%20Assistants%20Use%20Your%20Website.md).

## Why it matters to web specialists

- An agent using WebMCP reads your page's actions as names and descriptions. That copy is now something an AI reads to decide what to do, so it needs the same care as a button label.
- The removed form version had the agent read field names and allowed options straight from the form. Even without it, clear field names and limited choices make a form easier for any reader to use.
- Screenshot-and-click agents fail when layouts move. If your redesign shifts a button, an assistant that clicked it last week may miss it.
- Built-in summarizing and translating could show up in features you design. They run only in some Chrome versions, so other browsers need a working fallback.

## What you can do with it

These are my suggestions, not the speaker's.

- When a team proposes an AI feature, ask whether it needs a server model at all, or whether a built-in browser tool would do.
- Write action names and descriptions for WebMCP the way you write microcopy. Short, specific, one action each.
- Ask your engineers which browsers a built-in AI feature will work in, and what users of Firefox and Safari will see.
- If you test with an AI assistant clicking through your site, note where it gets lost. That's a sign the page structure is unclear to people too.

## Words worth knowing

- **Agent.** An AI that takes actions, like clicking or editing, instead of only answering.
- **WebMCP.** A proposed standard that lets a page list the actions an AI assistant may take on it.
- **On-device AI.** AI that runs on the user's computer, so text doesn't go to a server.
- **Model.** The AI system itself, the part that reads text and writes a reply.
- **Token.** A small piece of text. AI services charge by how many the model reads and writes, see [tokens](../Glossary.md#token).

## A line worth remembering

> "The application already knows what actions it supports. What if it could expose those directly?"
> Navya Agarwal
