---
type: talk-plain
event: AI Coding Summit
speaker: Maya Shavin
date: 2026-11-16
relevance: Medium
takeaway: A team turning PDFs into online forms got faster, steadier results by using AI for one step and plain rules for the rest, then having a person review each form.
tags:
  - conference-talk
  - plain-language
---
# Use AI Only Where You Need It

**Speaker.** Maya Shavin, Salesforce. AI Coding Summit, Nov 16.
**How much this matters to you.** Medium. It's about forms, labels and generating content at scale, which is your territory. The engineering details matter less for you.

## The idea in plain words

Her team had to turn a huge pile of PDF forms into online forms that match the PDF exactly. The source notes aren't sure of the size. She said 100,000 in the talk and 10,000 in the Q&A. Some were scanned and some were 20 years old.

The first try handed each PDF to one [agent](../Glossary.md#agent), an AI tool that decides its own steps, with a long [prompt](../Glossary.md#prompt) of rules and examples. They built it in under 24 hours, and its output matched the PDF 80 to 90% of the time. Then the problems showed up. The same form run on two machines came out with checkboxes on one and a dropdown on the other. An equipment form should ask for "operating system" only when the item is a laptop, and the agent put every question on one screen. Some fields worked but had misleading labels, which she called still unacceptable.

Her realization was that most of the job has no guesswork in it. Pulling text out of a PDF is a fixed task. So is adding the sections every form shares, and so is checking the result. Only one step needs AI, which is turning the cleaned-up content into the form itself. So they built a fixed sequence:

1. Pull the text out of the PDF with an ordinary tool and clean it. This also blocks [prompt injection](../Glossary.md#prompt-injection), hidden text in a PDF that tries to give the AI orders.
2. AI builds the form.
3. A program checks the structure. Does the laptop question exist? If not, try again, up to 3 times.
4. Add the shared parts and tidy up.
5. A person compares the form with the PDF and accepts, edits or rejects it.

In a side-by-side demo on a two-page form, the fixed sequence left 4 open questions for the reviewer and the agent left 8. The agent was also about 10 seconds slower on that one small form, which adds up across thousands. The host credited the approach with cutting migration time by about 90%. She was clear that this doesn't make the AI smarter. It means you know where it fails, and the AI has less room to [hallucinate](../Glossary.md#hallucination), to make things up.

## Why it matters to web specialists

- Checkboxes in one run and a dropdown in the next is a design consistency problem. Fixed rules and fixed templates are how you prevent it.
- A wrong label on a working field still fails the user. She counted it as a failure, and so should you.
- Conditional questions, the ones that appear only after a certain answer, are where the AI slipped. Check them first in any AI-built form.
- If you're asked to generate titles, descriptions or page copy for thousands of pages, her split applies directly. Keep the fixed parts fixed and let AI write only the part that needs judgment.

## What you can do with it

These are my suggestions, not the speaker's.

- Before you give a big job to an agent, write the steps on paper. Mark the one or two that need judgment. Ask an engineer whether the rest can be fixed rules or templates.
- Run the same input twice and compare. If the results differ, you've found a step that needs a rule.
- Follow her advice to look for where the agent will fail. Write each failure down as a rule, like "every field label must match the PDF word for word."
- Give reviewers a short checklist: labels, conditional questions, input types. That keeps your human review step from being a quick glance.

## Words worth knowing

- **Deterministic.** A [deterministic](../Glossary.md#deterministic) step gives the same result every time for the same input. Most of her sequence is deterministic.
- **Agent.** An AI tool that chooses its own next step.
- **Prompt injection.** Hidden instructions in content that try to take over the AI.
- **Hallucination.** When AI makes up something that isn't in the source.
- **Spec.** The written description of what to build. She keeps the [spec](../Glossary.md#spec) and rules current so the AI step has accurate context.

## A line worth remembering

> "We do not guarantee that we will improve the quality of the AI-generated response, but we do guarantee that we know where it fails."
> Maya Shavin
