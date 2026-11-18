---
type: talk-plain
event: AI Coding Summit
speaker: Victor Savkin
date: 2026-11-16
relevance: Low
takeaway: Automated checks get faster and cheaper when the system measures what each task really uses and skips work whose inputs didn't change, which matters more now that agents wait on those checks.
tags:
  - conference-talk
  - plain-language
---
# Keeping Automated Checks Fast and Cheap

**Speaker.** Victor Savkin, Nx and Polygraph. AI Coding Summit, Nov 16.
**Technical notes.** [[08 - Solving CI in the AI Agent|Full technical version]]
**How much this matters to you.** Low. This is about the plumbing engineers pay for. You won't set any of it up, but it explains why you sometimes wait on checks.

The source notes combine a silent screen recording with a transcript that has gaps. The answers to audience questions weren't captured, and the title may have been cut off.

## The idea in plain words

Every time someone proposes a code change, [[Glossary#CI|CI]] runs automatic checks on rented computers. Teams pay by the minute for those computers, whether they're busy or not. He said most setups use about 40% of what they pay for, "and 40% is generous."

He had three fixes. First, measure how much memory and processing each task needs, then pack tasks onto machines like someone filling gaps in a truck. That can take use from 40% to 80%. Second, put all the tasks in one shared line for all the machines, the way a bank has one line for many tellers. Third, and biggest, run less. The system watches which files each check actually reads. If you change a file the check never read, it reuses the old result. His example was a German translation file that one shop test never touched.

On his benchmark, the common shortcut of reusing old results roughly halves the cost. His team's approach brings a further 4.7 times reduction, about 9 times cheaper than a basic setup. He added, "Every repository is different." It's a private beta that requires Nx, his company's product.

He closed with a question. Agents now wait on these checks, not people. Should checks be as fast as possible, or as cheap as possible?

## Why it matters if you design or do SEO

- Each change you push starts a full round of checks that costs money. Ten tiny changes can cost more than one combined change. That's my inference from his talk, not his advice.
- He warned that skipping tests by guessing breaks a promise teams rely on, that a [[Glossary#Green check|green check]] on the [[Glossary#Main branch|main branch]], the official copy of the code, means it's safe. That promise is why the green check is worth trusting.
- If checks take 20 minutes, that's a setup problem engineers can work on. It doesn't mean your change is broken.

## What you can do with it

These are my suggestions, not the speaker's.

- Ask an engineer how long checks usually take on your project, so you know what's normal and when to ask for help.
- Ask whether the team prefers one combined change over many small ones. Some teams care, some don't.
- If your agent keeps re-running checks in a loop, stop it and ask someone. Each round costs time and money.

## Words worth knowing

- **CI.** The automatic checks that run on every proposed change.
- **Green check.** The mark that says every required check passed.
- **Main branch.** The official copy of the code the live product is built from.
- **Flaky test.** A [[Glossary#Flaky test|flaky test]] passes sometimes and fails sometimes with nothing changed. He said guessing which tests to skip struggles with these.

## A line worth remembering

> "Cheap is not as attractive in marketing, but being economical matters."
> Victor Savkin
