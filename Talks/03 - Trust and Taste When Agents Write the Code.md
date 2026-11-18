---
type: talk-plain
event: AI Coding Summit
speaker: Dominik Kundel
date: 2026-11-16
relevance: High
takeaway: Fix your real bottleneck instead of chasing every new AI tool, make agents show proof of their work, and bring the taste that decides what is worth shipping.
tags:
  - conference-talk
  - plain-language
---
# Trust and Taste When Agents Write the Code

**Speaker.** Dominik Kundel, OpenAI. AI Coding Summit, Nov 16.
**How much this matters to you.** High. Half the talk is about taste and visual proof, which is work web specialists already do.

## The idea in plain words

The official title was "What Comes After AI Coding." A year ago, Kundel says, the AI sat in a side panel and you reviewed every change. Now most people run several [agents](../Glossary.md#agent), AIs that do tasks on their own, at once. His first advice is calming. "You don't have to adopt every new thing; you don't have to feel like you're missing out." Ask what you can't get done today and where your time goes. Fix that, then move on.

He uses a personal agent from OpenAI called Dots. Almost every task now starts as a message to it. Once, driving to work, he talked a feature through with it by voice. By the time he parked, a design doc was in Slack. He commented, and it built the changes as a [pull request](../Glossary.md#pull-request), a proposed change that a person reviews before it goes in. When it does something he didn't expect, he asks it why. Was it missing information, a tool or a limit? One caveat. The transcript garbles "my Dot" as "my dad" and "my dog," so the source notes fixed it from context.

His second theme is trust. More agents means more changes, and you still own the result. Give the agent real [tests](../Glossary.md#test), meaning automatic checks, plus written user journeys it can click through. He wants agent changes to come with screenshots or a recording. On web projects a [deploy preview](../Glossary.md#deploy-preview), a private copy of the site with the change applied, is non-negotiable for him. Then close the loop. When you leave a review comment, ask why the agent made that mistake. Write the answer back into the project as a test, a written requirement or a [lint rule](../Glossary.md#lint-rule), an automatic style check.

His last theme is taste. "The world doesn't necessarily need more slop." Everyone carries a camera, yet people still hire photographers for weddings. Now six people often build the same prototype. Taste decides which one ships, and why.

## Why it matters to web specialists

- He says taste can be practiced. Play games and work out what makes them fun. Try competitors' products and say why they feel better. Learn the words for motion and color.
- In the Q&A he said every generated SaaS landing page turned purple. Models have a default look, and your job is to steer it.
- He called [skills](../Glossary.md#skill), saved instruction sets for an agent, "a good cop-out" when you lack design vocabulary. You end up with someone else's taste. You have the vocabulary.
- Engineers new to front-end look at two designs and say "close enough." You already see that nuance.

## What you can do with it

These are my suggestions, not the speaker's.

- Write your key user journeys in plain steps. Ask an engineer to store them in the project so agents can check against them.
- Ask that every agent-made change include screenshots or a recording and a deploy preview link. Review the preview, not the code.
- When you correct an agent, ask "why did you do that?" Then ask for the answer to become a written rule in the project's instruction file.
- Never accept the default look. Name the colors, spacing and motion you want, in words.
- Give an agent small, low-risk tasks first, like a new hire. That comparison is his.

## Words worth knowing

- **Agent.** An AI that does tasks for you, like editing files or clicking through an app.
- **Pull request.** A proposed change that someone reviews before it is accepted.
- **Deploy preview.** A private, working copy of the site with one change applied, for checking before release.
- **Lint rule.** An automatic check for style or common mistakes.

## A line worth remembering

> "Taste is the ability to describe what you like and to predict what other people will like."
> Dominik Kundel, quoting a colleague
