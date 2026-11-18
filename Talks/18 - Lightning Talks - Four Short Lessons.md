---
type: talk-plain
event: React Summit
speaker: Paul Bratslavsky, Geno Racklin Asher, Tucker Chapin, Jean-François Bisson
date: 2026-11-17
relevance: High
takeaway: Passing checks mean less when the AI wrote both the code and the tests, so automate the question of what a change touched, keep humans on whether it's what you wanted, and turn repeated review comments into automatic rules.
tags:
  - conference-talk
  - plain-language
---
# Lightning Talks - Four Short Lessons

**Speaker.** Paul Bratslavsky, Strapi. Geno Racklin Asher, Meticulous. Tucker Chapin, Render. Jean-François Bisson, Backtick. React Summit, Nov 17.
**Technical notes.** [[18 - Lightning Talks|Full technical version]]
**How much this matters to you.** High. The middle two talks are about reviewing AI work and enforcing design rules, and both land on your desk. The first and last matter less for you.

## The idea in plain words

Four sponsor talks, about six minutes each. Read Racklin Asher and Chapin first.

**Geno Racklin Asher, Meticulous.** Code got cheap, so the slow part became review. He said, without giving a source, that time spent reviewing [[Glossary#Pull request|pull requests]], the proposed changes someone has to approve, has gone up by over 50 percent. If Claude wrote a big change and its tests, and every check passed, would you merge it? Nobody he asked would. When one agent writes both, the [[Glossary#Green check|green check]] that says checks passed means less. Agents test too narrowly. Make a button bigger and the agent tests that the button is bigger, not the 20 pages that use it or the checkout page it now breaks. Perfect tests can't catch a wrong feature. His split is to automate the [[Glossary#Blast radius|blast radius]], everything a change affects, because that has an objective answer. Humans keep the job of judging intent.

**Tucker Chapin, Render.** His team kept leaving one review comment. Inline action buttons put the primary action first. Agents kept forgetting. One engineer fixed it by hand 11 times, then added a [[Glossary#Lint rule|lint rule]], an automatic check that flags a banned pattern. The problem stopped, and the rule caught 15 more cases. Agents follow lint messages "as gospel," so the message should explain the right fix. One badly worded message led agents to strip out error reporting that mattered. A rule should hold about 95 percent of the time. If people keep switching it off, move it back to docs or review.

**Paul Bratslavsky, Strapi.** He ran AI models on his own laptop, called [[Glossary#On-device AI|on-device AI]], for a music learning app. A summary took a minute and an answer 20 seconds, but a lesson took 7.5 minutes, so he moved lessons to Claude. He then shared his tools from Strapi, a content management system, through [[Glossary#MCP|MCP]], a standard way to plug tools and data into AI assistants.

**Jean-François Bisson, Backtick.** He asked Claude to add a feature to a [[Glossary#Vibe coding|vibe-coded]] phone app, built by prompting without reading the code, and it went straight to production.

These notes come from a Whisper transcript plus slide photos.

## Why it matters if you design or do SEO

- Button order is a design system rule. Chapin shows a design rule can become an automatic check nobody has to repeat in review.
- Racklin Asher's button example is your territory. A component change that looks fine on one page can break another.
- Bisson's demo shipped an AI change to every user with no review. That's the risk Racklin Asher describes.
- If your content lives in a content management system, Bratslavsky's setup lets AI agents use it directly.

## What you can do with it

These are my suggestions, not the speakers'.

- List review comments you make more than twice. Ask an engineer which could become lint rules, and write the "do this instead" sentence the agent will follow.
- On a component change, ask for every page that uses the component and check a few in the preview.
- On any AI change, ask whether it's what you wanted, not whether the checks passed.

## Words worth knowing

- **Green check.** The mark that says automated checks passed. It only proves what the checks test.
- **Blast radius.** Everything a change could affect, including pages you didn't touch.
- **Lint rule.** An automatic check that flags a pattern your team has banned.
- **Pull request.** A proposed change waiting for review and approval.
- **MCP.** A standard way to connect AI assistants to tools and data.

## A line worth remembering

> "Is this change what I wanted? Because that's the one question only you can answer."
> Geno Racklin Asher
