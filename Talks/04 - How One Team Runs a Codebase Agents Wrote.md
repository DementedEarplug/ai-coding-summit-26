---
type: talk-plain
event: AI Coding Summit
speaker: Piotr Karwatka
date: 2026-11-16
relevance: Medium
takeaway: One open-source team lets agents write all its code by having everyone write plans in the same format and by refusing any change that fails its automatic checks.
tags:
  - conference-talk
  - plain-language
---
# How One Team Runs a Codebase Agents Wrote

**Speaker.** Piotr Karwatka, Open Mercato. AI Coding Summit, Nov 16.
**How much this matters to you.** Medium. Most of it is about running agents at scale, but the parts on written plans and human review of new UI are where you fit in.

## The idea in plain words

Open Mercato is a free, open-source toolkit for building business apps. According to the host's introduction, it has about 1.1 million lines of code and none of them were written by a human. It has 130 to 140 or more contributors. The project started in September 2025 as an experiment to see if a large app could be built that way.

Karwatka walked through the stages. Plain one-off requests to the AI stopped working as the app grew. The biggest quality jump came from a [spec](../Glossary.md#spec), a written plan agreed before any building starts. He called it "one of the biggest quality changes." The key was that everyone writes specs in one consistent format, with use cases and data. Before that, mixed formats caused many problems.

Then a hackathon left them with more than 300 open change requests, too many to review in a day. So they built [skills](../Glossary.md#skill), saved instructions an agent follows for one job, that run on their own. One reviews code. One tests the app in a browser and posts the results, with screenshots, on the change request. Agents run in temporary copies of the app, up to 15 at once.

The safety net is more than 12,000 automatic tests that run on every change. That system is called [CI](../Glossary.md#ci), for continuous integration. When every check passes, the change gets a [green check](../Glossary.md#green-check) and can merge. He called CI "a way of saying no to agents." His advice: "If you haven't got CI yet, have an agent set it up."

## Why it matters to web specialists

- Specs in one shared format were the turning point. Use cases and user goals are things you already write.
- People can't review everything at this scale, so they sort. The review skill decides whether a change needs a human. New UI that needs human testing goes to QA. That is a likely role for designers.
- In more than 9 months they haven't seen agents rewrite tests to pass. [The Hugging Face talk](02%20-%20Making%20AI%20Run%20Fast%20in%20the%20Browser.md) saw the opposite. Two speakers, two experiences. We'd assume it can happen.
- He uses [CODEOWNERS](../Glossary.md#codeowners), a file that names who must approve changes to each part of the project. People must understand how the system works before they stop reading the code. He said skipping that might be fine for single-use tools, but "for production, it's definitely not."
- "Every system is safety-critical, to some point." He also warned that a file-deleting command posted in a GitHub issue comment "could be really a problem" if an agent acts on it.

## What you can do with it

These are my suggestions, not the speaker's.

- Ask your team whether there is a spec template. If not, offer one with sections for the user goal, use cases and what "done" looks like on screen.
- Ask to be listed as an owner for design system, content or page template files, so changes there wait for your approval.
- Ask that agent-tested changes post screenshots where you can see them, and look at them.
- Ask which kinds of change go to a human reviewer. Make sure new UI is on that list.

## Words worth knowing

- **Spec.** A written plan of what to build and why, agreed before work starts.
- **Skill.** A saved set of instructions an agent follows for one kind of job.
- **CI.** The system that runs automatic checks on every proposed change.
- **Green check.** The mark that shows every automatic check passed.
- **CODEOWNERS.** A file that says who must approve changes to which parts of a project.

## A line worth remembering

> "This is also a way of saying no to agents."
> Piotr Karwatka
