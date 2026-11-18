---
type: talk-plain
event: AI Coding Summit
speaker: Haldun (Hal) Anil
date: 2026-11-16
relevance: High
takeaway: When AI writes the code, a change request has to prove it works with screenshots, steps to try it and passing checks, and a person still has to decide whether the change should exist.
tags:
  - conference-talk
  - plain-language
---
# Prove It Works Before You Ship It

**Speaker.** Haldun "Hal" Anil, Vapi. AI Coding Summit, Nov 16.
**How much this matters to you.** High. If you're asked to open change requests with an AI agent, this talk tells you what a good one looks like, and most of it is screenshots and clear steps you already know how to make.

These notes come from a recording with no sound. They cover what was on the slides and the audience question board. The spoken answers are missing.

## The idea in plain words

Anil became an engineer for the feeling of making something work. Then AI tools took over his typing, bit by bit, until he wrote almost no code at all. "It just wasn't mine to write anymore."

At his old company, the team shipped more than ever. One [pull request](../Glossary.md#pull-request), the package of changes someone asks the team to accept, added over 30,000 lines and was expected to go live within the hour. No person wrote it, but he still had to read it, test it and maintain it. He was the one guarding quality, so he became the bottleneck. He quit his job as founding CTO with nothing lined up. He showed he wasn't alone. The State of Devs 2026 survey found 46% of developers say AI hasn't been good for their mental state. Faros AI counted 242.7% more incidents per pull request.

At his new job he asked the staff what [code review](../Glossary.md#code-review), the step where a person checks a change before it goes in, is even for now. His answer is that a pull request has to prove to the reviewer that it does what its ticket asked and what it claims. It proves this four ways.

- **Show it.** Screenshots or video for any change people can see.
- **Demo it.** Step-by-step instructions a person can follow, including edge cases.
- **Check it.** Automated [tests](../Glossary.md#test) and other checks must pass before anything merges.
- **Analyze it.** A bot compares the change against the ticket and against the pull request's own claims.

So review moved earlier. Reviewers used to read code line by line. Now they check the proof and judge the intent. That means the trade-offs, the scope, and whether the change should exist at all. His example was a system that moves customers off AI models that providers retire. Building it took about 1 part in 20 of the effort. Proving it took the rest. It moved hundreds of thousands of live assistants with better than 99.9999% success.

## Why it matters to web specialists

- Show it and Demo it are design and content skills. A clear before-and-after screenshot and five plain steps to try the change are exactly the proof he asks for.
- You are well placed to judge intent. Whether a page change matches the brief, the brand and the search goal is a question no bot can settle.
- An agent can produce a huge change in minutes. Huge changes are hard to prove. His 30,000-line example is the warning.
- A passing [green check](../Glossary.md#green-check) means the automated checks passed. It doesn't mean the page looks right or reads well. Your screenshots cover that.

## What you can do with it

These are my suggestions, not the speaker's.

- When you open a pull request, include before and after screenshots at phone and desktop width.
- Write "how to try it" steps in plain words, including the odd cases: empty states, long titles, error messages.
- Ask the agent to restate the ticket and list what it changed. Compare that list to what you asked for.
- Before you start an agent, reread the ticket. Ask yourself whether it's right, because building the wrong thing is now cheap and reviewing it isn't.
- Ask an engineer which checks are required to pass, and what each one checks.

## Words worth knowing

- **Pull request.** A proposed set of changes that others review before it joins the main code.
- **Code review.** A person reading and checking a change before it's accepted.
- **Test.** A small program that checks one thing still works.
- **Green check.** The mark that shows every automated check passed.
- **CI.** The system that runs those checks automatically on every change, see [CI](../Glossary.md#ci).

## A line worth remembering

> "A bot can check a PR against its ticket. Only a person can decide whether the ticket was right."
> Haldun Anil
