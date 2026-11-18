---
type: talk-plain
event: AI Coding Summit
speaker: Mike Grabowski
date: 2026-11-16
relevance: Medium
takeaway: AI agents check mobile apps by reading the accessibility tree, so clear labels on buttons and fields help the agent test your screens as much as they help screen reader users.
tags:
  - conference-talk
  - plain-language
---
# How Agents Test Mobile Apps

**Speaker.** Mike Grabowski, CEO of Callstack. AI Coding Summit, Nov 16.
**Technical notes.** [[05 - Cross-Platform Software Factory|Full technical version]]
**How much this matters to you.** Medium. Most of the talk is about machines and money, but one point is pure design work. The agent finds its way around an app through the accessibility labels.

## The idea in plain words

After an [[Glossary#Agent|agent]], an AI tool that edits code and runs commands on its own, changes an app, someone has to open the app and check the change works. On a website that's easy. The agent opens the page in an invisible browser on a cheap rented Linux computer. Mobile apps are harder. You install the app, deal with gestures and system pop-ups, and face many phones and OS versions. iOS apps also need a Mac. In his words, "You cannot run iOS on Linux VMs."

His company built a tool called agent-device. The agent builds the app, then asks agent-device for a snapshot of the screen. That snapshot is the [[Glossary#Accessibility tree|accessibility tree]], the list of buttons, labels and fields that a screen reader announces. The agent picks an item, say the sign-up button, taps it, and takes a new snapshot. Screenshots work too, but they cost far more, so at scale the text version wins.

The rest of the talk is about running many agents at once without wasting money. Each agent "leases" a phone or simulator so two agents never drive the same device. The agent runs on a cheap Linux machine and borrows a Mac or a real phone only when it needs one. By his rough numbers, a Mac costs ten times more per minute, and running everything on a Mac wastes about $100 per 50 runs.

He also listed checks you can build on top, such as comparing screenshots against the Figma file or the previous build, and [[Glossary#End-to-end test|end-to-end tests]], scripts that use the app the way a person would, written as plain-language steps. In the Q&A he described letting the agent explore an app once, saving what it did, and replaying that recording as a fixed script. That keeps results [[Glossary#Deterministic|deterministic]], meaning the same every run, and cuts down on [[Glossary#Flaky test|flaky tests]] that pass one day and fail the next for no reason.

A caveat from the source notes: they come from an auto-generated transcript. The name of the device-leasing library didn't come through, and the agent framework he used, eve, is probably from Vercel.

## Why it matters if you design or do SEO

- Accessibility labels now have two readers. A button with no name is a barrier for a screen reader user and a dead end for an agent trying to test your flow.
- Comparing each build against Figma is exactly the check a designer would want. He presented it as something teams can build, not something everyone has.
- He thinks people will read less code and "as long as it works" will become the standard. He admitted that "might seem disturbing, especially in some of the more secure environments." If fewer people read the code, what you check in the running app counts for more.
- For SEO the direct lesson is small, since this is about mobile apps. The idea carries to the web, though. See [[01 - Letting AI Assistants Use Your Website|Letting AI Assistants Use Your Website]].

## What you can do with it

These are my suggestions, not the speaker's.

- When you hand off a mobile design, write the accessibility label for every button, icon and field. Treat labels as part of the design.
- Ask an engineer whether your team's agents check screens with snapshots or screenshots. If snapshots, ask to see one for a screen you designed. Vague or missing labels show up right away.
- Ask whether anyone compares builds against the Figma file. If not, ask what it would take.
- When you review a test build on a phone, turn on VoiceOver or TalkBack and go through the main flow. What it reads out comes from the same accessibility tree the agent uses.

## Words worth knowing

- **Agent.** An AI tool that takes steps on its own until a task is done.
- **Accessibility tree.** The structured list of what's on screen, with names and roles, that screen readers and these agents read.
- **End-to-end test.** A script that uses the app start to finish, like a person would.
- **Deterministic.** Same input, same result, every time.
- **Flaky test.** A test that sometimes passes and sometimes fails with nothing changed.

## A line worth remembering

> "The snapshot is really the accessibility tree; that's why it's super important for your application to be accessible."
> Mike Grabowski
