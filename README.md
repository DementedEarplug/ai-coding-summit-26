---
type: conference-plain
events:
  - AI Coding Summit
  - JSNation
  - React Summit
attended: 2026-11-16
location: New York, NY
tags:
  - conference
  - plain-language
---
# AI Coding Summit + JSNation + React Summit 2026, plain-language version

This is a version of my conference notes for people who don't write code. It's for web specialists and anyone else being asked to use AI coding tools and contribute to a codebase without an engineering background.

The conference was three events in New York in November 2026. Most talks were aimed at engineers. Underneath the jargon, though, most of them were about something you deal with already. How do you know the work is right before it ships?

## How to read this

- **New to all of it?** Read [Working Safely with AI Agents](Working%20Safely%20with%20AI%20Agents.md) first. It's the practical guide, built from what the talks said.
- **Hit a word you don't know?** It's probably in the [Glossary](Glossary.md). Each talk note also explains its terms as it goes.
- **Curious about AI assistants using websites?** [WebMCP Explained](WebMCP%20Explained.md) covers the idea from the conference that matters most for design, accessibility and search.
- **Want the talks?** Each one has a short note below. Start with the ones marked High.

Each talk note has the same parts. It covers the idea in plain words, why it matters to you, what you can do with it and a few terms. The "what you can do" sections are my suggestions, not the speaker's.

## What the conference kept coming back to

**Writing code got cheap. Checking it didn't.** Nearly every speaker said this in some form. An agent can produce a change in minutes. Finding out whether it's right takes as long as ever, and sometimes longer. One speaker quoted research that "time saved writing is often re-spent auditing."

**A green check doesn't mean the work is right.** The automated checks only test what someone thought to test. When the same AI writes the change and the tests for it, passing proves even less. Four speakers made this point separately. One agent, told to make the checks pass, changed the checks instead of the code.

**The human job is intent and taste.** "Only a person can decide whether the ticket was right." Speakers kept handing people the same jobs. Decide what's worth building, judge whether it feels right and own what ships. That's design and content work.

**Write it down where the AI has to follow it.** Telling an agent "make no mistakes" doesn't work. What worked was something concrete it had to follow, like a named component, a plain-English test, a drawn flow or an automatic rule. A rule the agent reads and can forget is weaker than a rule that blocks it.

**Keep the AI's instructions short.** The people getting the best results kept their instruction files short, from about 30 to 120 lines. They added a rule only when something actually went wrong, usually more than once.

**Accessibility helps agents, but agents aren't the audience.** Some AI tools read a page's accessibility structure to understand it, so good labels help them. A participant on day 2 warned that what agents and people need "are going to diverge." Design for people first.

**A non-developer can ship, at a price.** One speaker's wife fixes bugs in his app by describing them to Claude, without him reading the code. He was clear that it works because the app has about five active users and he keeps backups. The same approach on a company site is a different risk.

## Talks

### Day 1, Nov 16

1. [Letting AI Assistants Use Your Website](Talks/01%20-%20Letting%20AI%20Assistants%20Use%20Your%20Website.md). Wes Bos. **High.** Websites listing their own actions so AI assistants stop guessing where to click.
2. [Making AI Run Fast in the Browser](Talks/02%20-%20Making%20AI%20Run%20Fast%20in%20the%20Browser.md). Joshua Lochner, Hugging Face. **Low.** Very technical, but its lesson about AI gaming its own tests applies everywhere.
3. [Trust and Taste When Agents Write the Code](Talks/03%20-%20Trust%20and%20Taste%20When%20Agents%20Write%20the%20Code.md). Dominik Kundel, OpenAI. **High.** Why taste is the human's job, and how to build trust in AI work.
4. [How One Team Runs a Codebase Agents Wrote](Talks/04%20-%20How%20One%20Team%20Runs%20a%20Codebase%20Agents%20Wrote.md). Piotr Karwatka, Open Mercato. **Medium.** What a fully automated team looks like, and the checks that keep it honest.
5. [How Agents Test Mobile Apps](Talks/05%20-%20How%20Agents%20Test%20Mobile%20Apps.md). Mike Grabowski, Callstack. **Medium.** Agents read the accessibility structure of an app, so good labels matter.
6. [Don't Let the AI Grade Its Own Work](Talks/06%20-%20Don't%20Let%20the%20AI%20Grade%20Its%20Own%20Work.md). Probably Vladimir Novick. **High.** Real stories of agents changing the rules to pass.
7. [Use AI Only Where You Need It](Talks/07%20-%20Use%20AI%20Only%20Where%20You%20Need%20It.md). Maya Shavin, Salesforce. **Medium.** A fixed step-by-step process beat a free-roaming agent.
8. [Keeping Automated Checks Fast and Cheap](Talks/08%20-%20Keeping%20Automated%20Checks%20Fast%20and%20Cheap.md). Victor Savkin, Nx. **Low.** Behind-the-scenes engineering about automated checks.
9. [AI Features That Run Inside the Page](Talks/09%20-%20AI%20Features%20That%20Run%20Inside%20the%20Page.md). Navya Agarwal, Adobe. **Medium.** AI that runs in the browser, and the second WebMCP talk of the day.
10. [Prove It Works Before You Ship It](Talks/10%20-%20Prove%20It%20Works%20Before%20You%20Ship%20It.md). Haldun Anil, Vapi. **High.** Pull requests should carry proof, like screenshots and steps to try it.

### Day 2, Nov 17

11. [Let the Browser Do the Work](Talks/11%20-%20Let%20the%20Browser%20Do%20the%20Work.md). Ameer Sami. **High.** Native HTML and CSS features that replace code, and why agents don't reach for them.
12. [Discussion Room - Setting Agents Up to Succeed](Talks/12%20-%20Discussion%20Room%20-%20Setting%20Agents%20Up%20to%20Succeed.md). Kent C. Dodds, Mark Erikson and others. **Medium.** Where rules for agents should live.
13. [Growing Your Career When AI Does the Technical Work](Talks/13%20-%20Growing%20Your%20Career%20When%20AI%20Does%20the%20Technical%20Work.md). Brittany Ellich, Bluesky. **High.** What gets people promoted when agents do the middle of the work.
14. [Panel - Web Jobs in the AI Era](Talks/14%20-%20Panel%20-%20Web%20Jobs%20in%20the%20AI%20Era.md). Kent C. Dodds, Mark Erikson, Shaundai Person and David Khourshid. **High.** How four experienced people decide how much to trust AI.
15. [Name Your Tools So the AI Doesn't Guess](Talks/15%20-%20Name%20Your%20Tools%20So%20the%20AI%20Doesn't%20Guess.md). Tanner Linsley. **Medium.** Naming exactly what to use in your request.
16. [Writing Tests in Plain English](Talks/16%20-%20Writing%20Tests%20in%20Plain%20English.md). Avindra Fernando. **High.** Acceptance criteria in plain English that an agent turns into tests.
17. [Map the Flow Before the AI Builds It](Talks/17%20-%20Map%20the%20Flow%20Before%20the%20AI%20Builds%20It.md). David Khourshid, Stately.ai. **High.** Drawing the states of a flow so the AI builds the right thing.
18. [Lightning Talks - Four Short Lessons](Talks/18%20-%20Lightning%20Talks%20-%20Four%20Short%20Lessons.md). Four speakers. **High.** Includes turning repeated review comments into automatic rules.
19. [A Non-Developer Ships Fixes with Claude](Talks/19%20-%20A%20Non-Developer%20Ships%20Fixes%20with%20Claude.md). Kaleb McKelvey, Netflix. **High.** The closest talk to your situation, with the setup that made it safe enough.

## If you only read five

1. [A Non-Developer Ships Fixes with Claude](Talks/19%20-%20A%20Non-Developer%20Ships%20Fixes%20with%20Claude.md), because it's your situation.
2. [Prove It Works Before You Ship It](Talks/10%20-%20Prove%20It%20Works%20Before%20You%20Ship%20It.md), because it tells you what good evidence looks like.
3. [Don't Let the AI Grade Its Own Work](Talks/06%20-%20Don't%20Let%20the%20AI%20Grade%20Its%20Own%20Work.md), because it shows what goes wrong.
4. [Writing Tests in Plain English](Talks/16%20-%20Writing%20Tests%20in%20Plain%20English.md), because you can write these.
5. [Let the Browser Do the Work](Talks/11%20-%20Let%20the%20Browser%20Do%20the%20Work.md), because it's the most design-relevant technical talk.

## Where speakers disagreed

- **Should anyone still read the code?** Kent C. Dodds has mostly stopped reading what his agents write and controls quality through checks instead. Mark Erikson still reads it and limits his speed so he can keep up. Both said it depends on the stakes. For anything with real users or private data, someone should still read it.
- **Can you trust the green check?** One team merges as soon as all checks pass. Another speaker showed agents editing the checks themselves. Both are right. A green check only means something if the agent couldn't change what it checks.
- **Is WebMCP an accessibility tool?** Some see AI assistants as a new way in for people with disabilities. A participant in the discussion room warned that agent needs and human needs will pull apart. My view is in [WebMCP Explained](WebMCP%20Explained.md).
- **Adopt everything new, or wait?** The OpenAI speaker said to fix your actual bottleneck instead of chasing every new workflow. Other talks were "try it tonight" pitches. I'd try the ones that fix something that's blocking you now.

## About these notes

Day 1 notes come from transcripts and slides. Some day 1 talks had slides but no audio, and those notes say so. Day 2 notes come from screen recordings I transcribed with speech-to-text, which can't tell speakers apart, so panel quotes name a speaker only when it was clear who spoke. Talk 19 I watched as a replay.

My full technical notes, with transcripts, aren't part of this repo.
