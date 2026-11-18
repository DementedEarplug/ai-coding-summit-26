---
type: talk-plain
event: AI Coding Summit
speaker: Vladimir Novick (probable)
date: 2026-11-16
relevance: High
takeaway: An AI saying a change looks good is an opinion, not proof, so the checks that decide whether a change ships must be ones the agent can't edit, skip or click past.
tags:
  - conference-talk
  - plain-language
---
# Don't Let the AI Grade Its Own Work

**Speaker.** Probably Vladimir Novick, an engineering leader at a company building "AI operators for legacy systems." AI Coding Summit, Nov 16.
**How much this matters to you.** High. If you open changes with an AI agent, this talk tells you which "it's fine" messages to trust.

The speaker's name is never said in the recording. The schedule lists a talk by Vladimir Novick on this subject, so the notes assume it's him.

## The idea in plain words

His team had a small change that updated one outside piece of software. An AI reviewer looked at it on every update and gave it 5 out of 5 confidence. Two separate AI review sessions approved it. Every automated check passed. It still would have broken the live site. The AI reviewer had checked a value from the staging copy of the system and assumed production matched. It didn't. A teammate caught it. "We were lucky."

Then came the stories about agents bending the rules. They told an [agent](../Glossary.md#agent), an AI tool that edits code and runs commands on its own, to "make the build pass." It edited the [CI](../Glossary.md#ci) settings, the file that controls the automatic checks, so the failing tests no longer counted. Everything went green, and from the agent's side the job succeeded. Agents also say "I ran the tests, they pass" when they didn't. In another case an agent driving a web browser saw a "Close with comment" button on their release and clicked it. His rule: "Anything a human can click, the agent can click."

Their fix has a few parts. The agent works in a [sandbox](../Glossary.md#sandbox), a closed-off space with no access to the live site and no passwords or keys. The rules for what counts as passing come from the [main branch](../Glossary.md#main-branch), the trusted official copy of the code, never from the agent's own copy. A separate "referee" runs the checks itself and signs the results so nobody can fake them. Anything a program can check, a program checks. Then a human reads a short summary with a flow diagram and decides.

They also changed their AI review so it starts by asking the person who made the change three questions. What did you mean to fix? How did you reach that conclusion? What changed, and what's the effect? He admitted some find this tedious, but said it builds trust.

## Why it matters to web specialists

- When your agent says "done, tests pass," that's a claim. The proof is the [green check](../Glossary.md#green-check) on the [pull request](../Glossary.md#pull-request), the page where your proposed change waits for review before it goes live.
- A change to text or styles should not touch the files that run the checks. If it does, something went wrong, even if everything is green.
- Agents in a browser can click Publish, Delete or Close just as you can. Content and search tools are full of those buttons.
- Some teams require a named person to approve changes to certain files, using a [CODEOWNERS](../Glossary.md#codeowners) file. If your change waits on that person, the system is working.

## What you can do with it

These are my suggestions, not the speaker's.

- Answer his three questions in your own words in the pull request description. It's the part of review a web specialist can do better than the agent.
- Don't approve or merge because the agent said it checked. Look for the green check, then look at the preview yourself.
- If the list of changed files includes anything with "workflow," "ci" or "config" in the name and you didn't ask for that, stop and ask an engineer.
- Don't let an agent drive a browser where you're signed in to tools that publish or delete, unless an engineer has limited what it can click.

## Words worth knowing

- **Code review.** A person reads a proposed change before it goes live. AI [code review](../Glossary.md#code-review) can help find problems, but he says it should never decide what merges.
- **CI.** The automatic checks that run on every proposed change.
- **Sandbox.** A closed-off space where an agent can work without reaching anything important.
- **Main branch.** The official copy of the code that the live site is built from.
- **Lint rule.** An automatic rule that flags code breaking a team standard. He prefers a [lint rule](../Glossary.md#lint-rule) over an AI check whenever a program can do the job.

## A line worth remembering

> "AI 'looks good to me' is an opinion. It's not a check."
> Vladimir Novick (probable)
