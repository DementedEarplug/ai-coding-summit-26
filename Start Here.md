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

This is a version of my conference notes for people who don't write code. It's for UX and UI designers, SEO specialists and anyone else being asked to use AI coding tools and contribute to a codebase without an engineering background.

The conference was three events in New York in November 2026. Most talks were aimed at engineers. Underneath the jargon, though, most of them were about something you deal with already. How do you know the work is right before it ships?

## How to read this

- **New to all of it?** Read [[Working Safely with AI Agents]] first. It's the practical guide, built from what the talks said.
- **Hit a word you don't know?** It's probably in the [[Glossary]]. Each talk note also explains its terms as it goes.
- **Curious about AI assistants using websites?** [[WebMCP Explained]] covers the idea from the conference that matters most for design, accessibility and search.
- **Want the talks?** Each one has a short note below. Start with the ones marked High.

Each talk note has the same parts. It covers the idea in plain words, why it matters to you, what you can do with it and a few terms. The "what you can do" sections are my suggestions, not the speaker's. Every note also links to my full technical version if you want the details.

## What the conference kept coming back to

**Writing code got cheap. Checking it didn't.** Nearly every speaker said this in some form. An agent can produce a change in minutes. Finding out whether it's right takes as long as ever, and sometimes longer. One speaker quoted research that "time saved writing is often re-spent auditing."

**A green check doesn't mean the work is right.** The automated checks only test what someone thought to test. When the same AI writes the change and the tests for it, passing proves even less. Four speakers made this point separately. One agent, told to make the checks pass, changed the checks instead of the code.

**The human job is intent and taste.** "Only a person can decide whether the ticket was right." Speakers kept handing people the same jobs. Decide what's worth building, judge whether it feels right and own what ships. That's design and content work.

**Write it down where the AI has to follow it.** Telling an agent "make no mistakes" doesn't work. What worked was something concrete it had to follow, like a named component, a plain-English test, a drawn flow or an automatic rule. A rule the agent reads and can forget is weaker than a rule that blocks it.

**Keep the AI's instructions short.** The people getting the best results kept their instruction files short, from about 30 to 120 lines. They added a rule only when something actually went wrong, usually more than once.

**Accessibility helps agents, but agents aren't the audience.** Some AI tools read a page's accessibility structure to understand it, so good labels help them. A participant on day 2 warned that what agents and people need "are going to diverge." Design for people first.

**A non-developer can ship, at a price.** One speaker's wife fixes bugs in his app by describing them to Claude, without him reading the code. He was clear that it works because the app has about five active users and he keeps backups. The same approach on a company site is a different risk.

## Talks

![[Plain Talks.base]]

### Day 1, Nov 16

1. [[01 - Letting AI Assistants Use Your Website|Letting AI Assistants Use Your Website]]. Wes Bos. **High.** Websites listing their own actions so AI assistants stop guessing where to click.
2. [[02 - Making AI Run Fast in the Browser|Making AI Run Fast in the Browser]]. Joshua Lochner, Hugging Face. **Low.** Very technical, but its lesson about AI gaming its own tests applies everywhere.
3. [[03 - Trust and Taste When Agents Write the Code|Trust and Taste When Agents Write the Code]]. Dominik Kundel, OpenAI. **High.** Why taste is the human's job, and how to build trust in AI work.
4. [[04 - How One Team Runs a Codebase Agents Wrote|How One Team Runs a Codebase Agents Wrote]]. Piotr Karwatka, Open Mercato. **Medium.** What a fully automated team looks like, and the checks that keep it honest.
5. [[05 - How Agents Test Mobile Apps|How Agents Test Mobile Apps]]. Mike Grabowski, Callstack. **Medium.** Agents read the accessibility structure of an app, so good labels matter.
6. [[06 - Don't Let the AI Grade Its Own Work|Don't Let the AI Grade Its Own Work]]. Probably Vladimir Novick. **High.** Real stories of agents changing the rules to pass.
7. [[07 - Use AI Only Where You Need It|Use AI Only Where You Need It]]. Maya Shavin, Salesforce. **Medium.** A fixed step-by-step process beat a free-roaming agent.
8. [[08 - Keeping Automated Checks Fast and Cheap|Keeping Automated Checks Fast and Cheap]]. Victor Savkin, Nx. **Low.** Behind-the-scenes engineering about automated checks.
9. [[09 - AI Features That Run Inside the Page|AI Features That Run Inside the Page]]. Navya Agarwal, Adobe. **Medium.** AI that runs in the browser, and the second WebMCP talk of the day.
10. [[10 - Prove It Works Before You Ship It|Prove It Works Before You Ship It]]. Haldun Anil, Vapi. **High.** Pull requests should carry proof, like screenshots and steps to try it.

### Day 2, Nov 17

11. [[11 - Let the Browser Do the Work|Let the Browser Do the Work]]. Ameer Sami. **High.** Native HTML and CSS features that replace code, and why agents don't reach for them.
12. [[12 - Discussion Room - Setting Agents Up to Succeed|Discussion Room - Setting Agents Up to Succeed]]. Kent C. Dodds, Mark Erikson and others. **Medium.** Where rules for agents should live.
13. [[13 - Growing Your Career When AI Does the Technical Work|Growing Your Career When AI Does the Technical Work]]. Brittany Ellich, Bluesky. **High.** What gets people promoted when agents do the middle of the work.
14. [[14 - Panel - Web Jobs in the AI Era|Panel - Web Jobs in the AI Era]]. Kent C. Dodds, Mark Erikson, Shaundai Person and David Khourshid. **High.** How four experienced people decide how much to trust AI.
15. [[15 - Name Your Tools So the AI Doesn't Guess|Name Your Tools So the AI Doesn't Guess]]. Tanner Linsley. **Medium.** Naming exactly what to use in your request.
16. [[16 - Writing Tests in Plain English|Writing Tests in Plain English]]. Avindra Fernando. **High.** Acceptance criteria in plain English that an agent turns into tests.
17. [[17 - Map the Flow Before the AI Builds It|Map the Flow Before the AI Builds It]]. David Khourshid, Stately.ai. **High.** Drawing the states of a flow so the AI builds the right thing.
18. [[18 - Lightning Talks - Four Short Lessons|Lightning Talks - Four Short Lessons]]. Four speakers. **High.** Includes turning repeated review comments into automatic rules.
19. [[19 - A Non-Developer Ships Fixes with Claude|A Non-Developer Ships Fixes with Claude]]. Kaleb McKelvey, Netflix. **High.** The closest talk to your situation, with the setup that made it safe enough.

## If you only read five

1. [[19 - A Non-Developer Ships Fixes with Claude|A Non-Developer Ships Fixes with Claude]], because it's your situation.
2. [[10 - Prove It Works Before You Ship It|Prove It Works Before You Ship It]], because it tells you what good evidence looks like.
3. [[06 - Don't Let the AI Grade Its Own Work|Don't Let the AI Grade Its Own Work]], because it shows what goes wrong.
4. [[16 - Writing Tests in Plain English|Writing Tests in Plain English]], because you can write these.
5. [[11 - Let the Browser Do the Work|Let the Browser Do the Work]], because it's the most design-relevant technical talk.

## Where speakers disagreed

- **Should anyone still read the code?** Kent C. Dodds has mostly stopped reading what his agents write and controls quality through checks instead. Mark Erikson still reads it and limits his speed so he can keep up. Both said it depends on the stakes. For anything with real users or private data, someone should still read it.
- **Can you trust the green check?** One team merges as soon as all checks pass. Another speaker showed agents editing the checks themselves. Both are right. A green check only means something if the agent couldn't change what it checks.
- **Is WebMCP an accessibility tool?** Some see AI assistants as a new way in for people with disabilities. A participant in the discussion room warned that agent needs and human needs will pull apart. My view is in [[WebMCP Explained]].
- **Adopt everything new, or wait?** The OpenAI speaker said to fix your actual bottleneck instead of chasing every new workflow. Other talks were "try it tonight" pitches. I'd try the ones that fix something that's blocking you now.

## About these notes

Day 1 notes come from transcripts and slides. Some day 1 talks had slides but no audio, and those notes say so. Day 2 notes come from screen recordings I transcribed with speech-to-text, which can't tell speakers apart, so panel quotes name a speaker only when it was clear who spoke. Talk 19 I watched as a replay.

My full technical notes, with transcripts, are in the folder above this one.
