---
type: talk-plain
event: React Summit
speaker:
  - Kent C. Dodds
  - Mark Erikson
  - Shaundai Person
  - David Khourshid
date: 2026-11-17
relevance: High
takeaway: Four experienced developers disagree on how much to trust AI agents, but all agree people still decide what's worth building and still own security, private data and judgment.
tags:
  - conference-talk
  - plain-language
---
# Panel - Web Jobs in the AI Era

**Speaker.** Kent C. Dodds, Epic Web. Mark Erikson, Replay. Shaundai Person, Netflix. David Khourshid, Stately.ai. React Summit, Nov 17.
**Technical notes.** [[14 - Panel - Web Dev Jobs in the AI Era|Full technical version]]
**How much this matters to you.** High. One panelist names user experience and "the art part" as the work people keep, and another says outright that non-technical people can't yet work the way he does.

## The idea in plain words

A moderator, not named in the audio, asked four developers how AI changed their jobs. The schedule listed Jack Herrington, but the fourth panelist was David Khourshid. The transcription tool can't tell speakers apart, so quotes carry a name only where the speaker was clear.

Kent C. Dodds has gone furthest. On a solo project with no SOC 2, a common security audit, he pasted a loosely written feature request into an [[Glossary#Agent|agent]], an AI tool that writes code with little supervision. Three hours later it "nailed it." He reviews an agent's work until he's never correcting it, then stops. Now he doesn't see the work until it's live. He admits non-technical people can't yet work this way, though he isn't sure that will matter "a year from now."

Mark Erikson went the other way on purpose. He caps himself at about three times his old pace and reads most of what the agent writes, so he keeps the system in his head. "We barely reviewed code when we were writing it by hand. And now we have 10 times as many PRs. Who's reviewing that code?" A PR, or [[Glossary#Pull request|pull request]], is a proposed change waiting for someone to check it.

Shaundai Person described Netflix. Early on, a tidy codebase turned into "a code base of comments." That made the AI worse, because it copies patterns. Her team now writes down shared standards and agrees on what goes to agents. She called that their [[Glossary#Harness|harness]], the rules, tools and checks around an agent.

David Khourshid wants some friction. An agent asks "A or B?", you don't understand the question, so you press A. That's the trap.

They disagreed on speed and on reading code. All four agreed that people still decide what's worth building and still own security, data handling and judgment.

## Why it matters if you design or do SEO

- Shaundai points worried people toward "the art part," user experience and judging value, because "only people can make that determination." That's your work.
- David says agents skip performance and security unless you ask. "Your app will be slow by default if you don't ask it." Slow pages are an SEO problem, so this one lands on you.
- One panelist's old company lost million-dollar deals after customer feedback got filtered out. The lesson was to walk through the app as the user and "make it one click."
- Shaundai warns that new apps collect a lot of personal data. "This is real information about real people." If you add tracking scripts or forms, that includes you.
- Kent says to keep each [[Glossary#Secret|secret]], a password or key, where the agent "can reference but cannot access."

## What you can do with it

Our suggestions, drawn from the panel.

- When an agent offers options you don't follow, ask it to explain each one in plain words before you pick. Kent says "we have a discussion" rather than taking its recommendation.
- Ask the agent directly to check page speed and accessibility. The panel named performance and security, and we'd add accessibility to the list.
- Ask an engineer where your team's written standards live, and point the agent at them.
- Before adding a form or tracking tag, ask who reviews privacy.
- Never paste passwords or keys into a chat with an agent.
- Pick your own pace. Mark's three times is a fine target.

For the career side, read [[13 - Growing Your Career When AI Does the Technical Work|growing your career]].

## Words worth knowing

- **Agent.** An AI tool that carries out multi-step work, like editing code, on its own.
- **Harness.** The setup around an agent: its instructions, tools and automatic checks.
- **Pull request.** A proposed change to shared code that teammates check first. Mark's "PRs."
- **Secret.** A password or key that grants access to a system and must stay hidden.

## A line worth remembering

> "A little bit of friction is still going to be good even as you cede more control to AI."
> David Khourshid
