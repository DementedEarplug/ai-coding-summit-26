---
type: guide
conference: "[[Start Here|AI Coding Summit + JSNation + React Summit 2026, plain-language version]]"
tags:
  - conference
  - plain-language
---
# Working safely with AI agents

This is a practical guide for designers, SEO specialists and anyone else who's been asked to change a codebase with an AI agent and no engineering background. It pulls together what nineteen conference sessions said about doing this without breaking things.

The talks were aimed at engineers, so some of the advice here is my translation of theirs. Where a speaker said it, the talk is linked. Where it's my own suggestion, I say so.

## The situation, honestly

Agents made writing code cheap. Almost every talk said the same thing next. Checking that the code is right is now the slow, expensive part. Haldun Anil quoted a research finding that "time saved writing is often re-spent auditing." ([[10 - Prove It Works Before You Ship It|Anil]])

That matters for you because an agent will happily produce a change that looks finished. It will tell you it's done. The automated checks may even pass. None of that proves the change does what you asked, looks right, or didn't break something on another page.

The good news is that the part only a person can do is the part you're already good at. Anil put it as "Only a person can decide whether the ticket was right." Dominik Kundel of OpenAI defined taste as "the ability to describe what you like and to predict what other people will like," and said it's the human's job. ([[03 - Trust and Taste When Agents Write the Code|Kundel]]) You know what the user needs, what the page should say and how it should feel. That's the judgment the agent can't supply.

## What you already bring

- **Intent.** You know what the change is for. Engineers often don't.
- **Taste.** When you ask an agent for a design, you get its taste, not yours. Kundel's warning was that you adopt the model's taste unless you bring your own. Give it your references, your design system and your rules.
- **Accessibility.** You likely know more about labels, contrast and focus order than the agent will check on its own. Agents read pages through the [[Glossary#Accessibility tree|accessibility tree]], so good labels help them too. ([[05 - How Agents Test Mobile Apps|Grabowski]])
- **Content and search.** Headings, page titles, link text and descriptions are your territory. An agent restyling a page can quietly change them. *(My point, not from a talk.)*

## Before you start

### Pick the right first tasks

My suggestion is to start with changes where a mistake is visible and cheap to undo.

Good first tasks:
- copy and microcopy changes
- alt text, labels and link text
- page titles, meta descriptions and heading fixes
- spacing, color and type adjustments that use existing design tokens
- a new variant of an existing component

Tasks to leave to an engineer, or do only with one beside you:
- anything involving login, passwords, payments or personal data
- deleting or migrating data
- anything in the automated checks or build settings
- adding a new [[Glossary#Library|library]]
- changes to a shared component used on many pages, unless you can check every page

Mark Erikson, a long-time React maintainer, put the limit on himself, not just on beginners. He caps how fast he goes so he can keep the whole system in his head. ([[14 - Panel - Web Jobs in the AI Era|panel]])

### Ask your engineers five questions

These come from what the speakers said a good setup needs. The questions are mine.

1. **Is there a [[Glossary#CLAUDE.md|CLAUDE.md]] or agents file?** It tells the agent how this project works. Without one, the agent guesses. Kaleb McKelvey's is a 120-line map that tells the agent what to read for each kind of task. ([[19 - A Non-Developer Ships Fixes with Claude|McKelvey]])
2. **Do pull requests get a [[Glossary#Deploy preview|deploy preview]]?** That's a link where you can click through your change before it goes live. It's the best place for you to review.
3. **Which checks are required before merging?** And what does each one check?
4. **Who reviews my pull requests, and what do they want to see in them?**
5. **What should I never touch?** Get the list of folders and files. Ask whether they're protected with [[Glossary#CODEOWNERS|CODEOWNERS]] so an agent can't change them by accident.

## Writing the request

A [[Glossary#Prompt|prompt]] for an agent works like a good ticket. "Make no mistakes" doesn't help. Three day-2 speakers each got better results by writing something down for the agent to follow. Linsley named the library, Fernando wrote a playbook and Khourshid drew a model of the app. ([[15 - Name Your Tools So the AI Doesn't Guess|Linsley]], [[16 - Writing Tests in Plain English|Fernando]], [[17 - Map the Flow Before the AI Builds It|Khourshid]])

Put these in every request:

- **The goal, in one sentence.** Who is this for and what should they be able to do?
- **What done looks like.** Write it as [[Glossary#Acceptance criteria|acceptance criteria]]. "Given a user on the pricing page, when they tab to the plan cards, then each card shows a visible focus ring." Avindra Fernando had an agent turn exactly this kind of plain-English line into automated tests. ([[16 - Writing Tests in Plain English|Fernando]])
- **The exact components or libraries to use.** Tanner Linsley calls these "magic words." Naming the design system component brings years of solved problems. Leaving it out lets the agent pick, and it may pick something the team doesn't use. ([[15 - Name Your Tools So the AI Doesn't Guess|Linsley]])
- **What not to touch.** "Only change files in the pricing page. Don't add libraries. Don't change any test or check settings."
- **Accessibility and performance, out loud.** On the jobs panel, David Khourshid said agents won't handle performance or security unless you ask: "Your app will be slow by default if you don't ask." I'd treat accessibility the same way and ask for keyboard support, labels and contrast by name. ([[14 - Panel - Web Jobs in the AI Era|panel]])
- **Prefer what the browser already does.** Ameer Sami asked an agent to replace a tooltip library with native browser features, and it suggested more libraries, then the plain `title` attribute. Agents fall back on old habits. If you know the browser can do it, such as a native popover or dialog, say so. ([[11 - Let the Browser Do the Work|Sami]])

For flows with several states, sketch them. Empty, loading, error, success, and what moves between them. Khourshid's whole talk was that an explicit model in the middle, a [[Glossary#Statechart|statechart]], beats a prompt. You already draw these as user flows. Paste the flow into the request. ([[17 - Map the Flow Before the AI Builds It|Khourshid]])

## While the agent works

- **Never paste a [[Glossary#Secret|secret]].** No passwords, API keys or tokens in the chat. Kent C. Dodds's rule is that the agent can refer to a secret by name but never read it. ([[14 - Panel - Web Jobs in the AI Era|panel]])
- **Watch for edits to the checks.** One agent told to "make CI pass" edited the check settings so failures were ignored. Another closed a release pull request because nothing stopped it from clicking the button. If the agent touches anything in a `.github` folder, a test file or a config file you didn't ask about, stop and ask an engineer. ([[06 - Don't Let the AI Grade Its Own Work|Novick]])
- **Watch for new libraries.** If the agent says it's installing something, ask why and whether the project already has a way to do it.
- **Stop it when the change grows.** A copy change that touches fifteen files isn't a copy change anymore.

## Checking the result without reading code

You don't need to read the [[Glossary#Diff|diff]] line by line. You need evidence. These are my suggestions, built on what the talks said counts as proof.

1. **Ask the agent to explain the change in plain words.** "List every file you changed, what you changed in each, and why. Tell me anything you weren't sure about."
2. **Use a fresh session to check it.** Open a new chat and ask it to compare the change against your acceptance criteria. Four speakers made the same point. A [[Glossary#Green check|green check]] from the agent that wrote the code proves less, and its own tests are too narrow. ([[18 - Lightning Talks - Four Short Lessons|Racklin Asher]], [[06 - Don't Let the AI Grade Its Own Work|Novick]])
3. **Click through the deploy preview.** Do the task the way a user would. Then do it with only the keyboard. Then at 200% zoom and at phone width.
4. **Check the [[Glossary#Blast radius|blast radius]].** If you changed a shared component, ask the agent "which pages use this?" and look at each one. Geno Racklin Asher's example was a test that checked the button got bigger, while the checkout page it broke went unchecked. ([[18 - Lightning Talks - Four Short Lessons|Racklin Asher]])
5. **Run a quick accessibility pass.** An automated checker plus a screen reader on the one thing you changed.
6. **For SEO-sensitive pages, check what's invisible.** Page title, meta description, heading order, canonical link, structured data and link text. A visual change can move these. *(My suggestion.)*

## Opening the pull request

Anil's rule was that review now means checking evidence, not reading thirty thousand lines. Give reviewers the evidence. ([[10 - Prove It Works Before You Ship It|Anil]])

- **Keep it small.** One change per [[Glossary#Pull request|pull request]].
- **Show it.** Before and after screenshots, or a short screen recording.
- **Say how to try it.** The steps to see the change in the preview.
- **Say what you checked.** Keyboard, zoom, screen reader, other pages that use the component.
- **Say what you're unsure about.** Reviewers can focus there. That's more useful than sounding confident.

## After review

When an engineer leaves the same comment on your work more than once, ask whether it can become a rule the agent follows automatically. Tucker Chapin's team fixed the same button-order comment by hand 11 times. A [[Glossary#Lint rule|lint rule]] stopped it and found 15 more cases. The talk's point was the repeats. A comment that comes up once can stay a comment. ([[18 - Lightning Talks - Four Short Lessons|Chapin]])

Chapin also said agents follow lint messages "as gospel." So a good rule says what to do instead, not just what's wrong. If you know the right answer, like "use the Button component's `secondary` variant," help write the message.

## Red flags

Stop and get an engineer when the agent:

- says it's done but can't show you the result
- deleted, skipped or loosened a test to make things pass, which is called [[Glossary#Reward hacking|reward hacking]]
- changed files in `.github`, test settings or build settings
- added a library you didn't ask for
- changed many more files than the task needs
- changed pages you didn't mention
- claims tests pass, but you never saw them run

## What to push back on

- **Merging without anyone reviewing.** McKelvey's wife ships fixes to his app from a prompt without him reading the code. He was clear that it's a risk choice. He has database backups and about five active users. Your company's site is a different risk. ([[19 - A Non-Developer Ships Fixes with Claude|McKelvey]])
- **"Just vibe it."** [[Glossary#Vibe coding|Vibe coding]] is fine for a prototype or a personal tool. For anything with real users, someone has to check it.
- **Everyone using AI their own way.** Shaundai Person said that at Netflix, people used AI with no shared standards, and a well-organized codebase turned into "a code base of comments." The fix was written standards and team agreement. Ask your team for the shared setup instead of inventing your own. ([[14 - Panel - Web Jobs in the AI Era|panel]])

## One-page checklist

- [ ] The task is small and a mistake would be visible and cheap
- [ ] I know which files I'm allowed to change
- [ ] The request has a goal, acceptance criteria, named components and a "don't touch" list
- [ ] I asked for accessibility by name
- [ ] No secrets in the chat
- [ ] The agent didn't touch tests, checks or build settings
- [ ] The agent explained every changed file in plain words
- [ ] A fresh session checked the change against my criteria
- [ ] I clicked through the preview, keyboard only, at 200% zoom and at phone width
- [ ] I checked every page that uses a changed component
- [ ] For SEO pages, title, meta, headings and structured data are unchanged or intended
- [ ] The pull request has screenshots, steps to try it and what I checked
- [ ] If I get the same review comment twice, I ask for a rule
