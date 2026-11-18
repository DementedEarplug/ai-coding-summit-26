---
type: talk-plain
event: React Summit
speaker: Ameer Sami
date: 2026-11-17
relevance: High
takeaway: Browsers can now handle dropdowns, tooltips, pop-up panels and readable text colors on their own, but AI agents rarely suggest these features, so you have to name them.
tags:
  - conference-talk
  - plain-language
---
# Let the Browser Do the Work

**Speaker.** Ameer Sami, S&C Electric Company. React Summit, Nov 17.
**How much this matters to you.** High. These are built-in browser features for the exact components you design, and the agent won't use them unless you ask by name.

These notes come from a recording transcribed by a speech-to-text tool. Some words were unclear. The browser support claims are the speaker's.

## The idea in plain words

Sami's claim is "less JavaScript," not "no JavaScript." JavaScript is the code that makes pages interactive. For years, teams wrote lots of it to build dropdowns, tooltips and pop-up panels. Browsers now do much of that with plain HTML and CSS, the markup and styling languages.

The problem is the AI. His team asked an [agent](../Glossary.md#agent) to replace a tooltip [library](../Glossary.md#library), a ready-made package of someone else's code, with modern browser features. The agent suggested another library. After more back and forth it suggested the plain `title` attribute. "The AI failed, plain and simple." He mentioned a Google [skill](../Glossary.md#skill), a set of instructions you load into an agent, that teaches agents these features. Even with it, he said, you can't count on the agent picking them. People have to know them.

He rebuilt three pages to show what changes.

- **A product page.** It had color chips, a tinted image background and a custom dropdown. A new CSS feature called `contrast-color()` picks black or white text for each chip so it stays readable. It meets the WCAG AA minimum contrast, but it picks wrong for some mid-tone colors. The custom dropdown, hundreds of lines long, became the browser's own select menu, now fully styleable. Firefox hasn't shipped that styling yet. The page lost about 43% of its JavaScript.
- **An article page.** The hero image now switches with light and dark mode on its own. Tooltips that needed six event listeners each now open on hover with a built-in delay. That hover feature, called interest invokers, is still experimental. Pop-ups also reposition themselves when they would run off screen. About 38% less JavaScript.
- **A date range picker.** The panel became a popover, a box that opens on top of the page and closes when you click elsewhere. Anchor positioning pins it under the field. CSS alone highlights the dates between start and hover, and a view transition animates the month change. Only about 7% fewer lines, but he says it would be about 57% if the original had animation. He also said the old way of showing the panel was "not good for accessibility."

For older browsers, his advice was to check [Baseline](../Glossary.md#baseline) status. "Widely available" means a feature has worked in all major browsers for about 30 months, and you can just use it. "Newly available" is more recent.

## Why it matters to web specialists

- Popovers, anchored menus, native selects and theme-aware images are the components on your screens. Knowing they exist changes what you can ask for.
- Built-in parts come with behavior a hand-built version has to fake, like closing on an outside click. His accessibility comment on the old panel is one example.
- `contrast-color()` is a quick win for text on colors pulled from data, but it can pick wrong on mid-tones. Check those against [WCAG](../Glossary.md#section-508-and-wcag) yourself.
- Less JavaScript usually means pages load faster. That's my inference, not a claim from the talk, but it matters for search.

## What you can do with it

These are my suggestions, not the speaker's.

- When you hand a component to an agent, name the feature. "Use the native popover and anchor positioning, no new library."
- Ask the agent to say whether each feature is Baseline widely available or newly available, and what happens in browsers that lack it.
- In the preview, test the dropdowns and popovers with a keyboard and in dark mode.
- Ask an engineer whether a custom dropdown or tooltip library could go. A smaller codebase is easier for everyone, agents included.

## Words worth knowing

- **Library.** Code someone else wrote that a project pulls in.
- **Baseline.** A label showing which browser features work everywhere, and for how long.
- **Skill.** A packet of instructions an agent loads for a specific job.
- **Agent.** An AI that writes and changes code for you.
- **WCAG.** The web accessibility guidelines, including the contrast rules.

## A line worth remembering

> "Agents are non-deterministic. There's no guarantee that they will always recommend the newest, latest browser API."
> Ameer Sami
