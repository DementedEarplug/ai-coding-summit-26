---
type: talk-plain
event: AI Coding Summit
speaker: Avindra Fernando
date: 2026-11-17
relevance: High
takeaway: Write what a feature should do in plain English, let an agent turn that into tests, and compare it with what the code really does to find bugs nobody wrote down.
tags:
  - conference-talk
  - plain-language
---
# Writing Tests in Plain English

**Speaker.** Avindra Fernando, principal architect at Taprobane Consulting. AI Coding Summit, Nov 17.
**Technical notes.** [[16 - Playbook-Based E2E Testing with Playwright|Full technical version]]
**How much this matters to you.** High. His tests are plain sentences a designer can read and check, and his method works best when the screens are built accessibly.

## The idea in plain words

Fernando asked the room who had deleted or commented out a failing test instead of working out what it meant. Many hands went up, his too.

His problem is drift. A team writes [[Glossary#Acceptance criteria|acceptance criteria]], the checklist that says when a feature counts as done, and later writes [[Glossary#End-to-end test|end-to-end tests]], scripts that click through the site like a visitor. A year on, some tests fail, some turn [[Glossary#Flaky test|flaky]], passing one run and failing the next, and nobody knows which requirement a test came from. Worse, some still pass but no longer check the requirement.

His fix works from both ends. Top down, an [[Glossary#Agent|AI agent]] reads the acceptance criteria and writes [[Glossary#Spec|specs]], plain English tests in a "given, when, then" shape. Bottom up, it reads the code and writes specs for what the code really does. The two never match, and the gaps are the point. The rules live in one file he calls a playbook. The team maintains only the playbook, and the agent regenerates everything else. A tool called the Playwright CLI turns each spec into clicks in a real browser.

His demo app tracks conference submissions. The bottom-up scan listed behavior nobody had written down. The form saved an end date before the start date. A name made only of spaces got saved as a blank row. Notes were saved but never shown. Deleting a conference had no confirmation step. A plain English spec took 48 seconds against 1.4 seconds for a regular test. His bet is that less drift saves more. These notes come from a Whisper transcript of the stream and photos of the slides.

## Why it matters if you design or do SEO

- You can read these specs. One from his demo said "Given no conferences are being tracked. When I open the app. Then it says 'No conferences yet. Add one to get started.'" That's a test of your empty state copy.
- His playbook bans hidden test IDs. Tests find buttons by role and label, the way a user does. That rule turned up buttons with no accessible name, and the agent proposed a story to fix them.
- Every bug his scan found is a UX bug. A person has to decide which gaps matter.
- He said testing animations this way isn't mature yet. A fade can look like a failure. The host suggested smaller tests or [[Glossary#Visual regression|visual regression testing]], which compares screenshots, and he agreed.
- Short, specific sentences like "click the name field" keep results [[Glossary#Deterministic|deterministic]], the same every run.

## What you can do with it

These are my suggestions, not his.

- Write acceptance criteria as "given, when, then" sentences, like "Given a saved conference, when I press delete, then I see a confirmation."
- Ask the agent for plain English specs from your criteria, and read them first.
- Ask engineers whether tests find elements by role and label. If so, a missing label fails a test.
- Offer to triage the gap list. He said the first pass needs people to review every gap.
- Never let your agent delete a failing test you don't understand. Ask an engineer.

## Words worth knowing

- **End-to-end test.** A script that uses the site like a visitor, in a real browser.
- **Spec.** Here, a plain English description of one behavior that a tool can run as a test.
- **Acceptance criteria.** The conditions a feature must meet to count as done.
- **Flaky test.** A test that passes and fails at random.
- **Deterministic.** Gives the same result every time.

## A line worth remembering

> "We don't necessarily have to have knowledge of TypeScript or any programming language anymore to maintain specs like this. This is simple English."
> Avindra Fernando
